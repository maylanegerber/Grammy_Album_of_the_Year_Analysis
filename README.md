## Case Study Report: An Analysis of Grammy-Nominated Artists Using Spotify Data
## Introduction:
The Grammy Awards aim to celebrate excellence in music, but their selections often spark controversy—none more so than the 2025 Album of the Year win by Beyoncé, honoring albums released in 2024. Like many fans and critics, I questioned whether other nominees, including Billie Eilish, Sabrina Carpenter, Charli XCX, Chappell Roan, Taylor Swift, Jacob Collier, and André 3000, delivered albums that resonated more with listeners. I used Spotify audio data and machine learning models to explore whether measurable sonic traits and popularity metrics support or challenge the Grammy’s final decision.

## Background:
I gathered song-level data for the 2024 Album of the Year nominees using the Spotify API. This included features such as popularity, danceability, energy, speechiness, acousticness, instrumentalness, tempo, valence, loudness, and liveness. Alongside exploratory analysis, I applied multiple linear regression, Random Forest, and XGBoost models to evaluate what factors drive popularity and how each artist’s album aligns with those traits.

## Objective:
My goal was to determine whether the Grammy-winning album differed in meaningful ways from the other nominated works and to identify which audio features most influence song popularity. I also wanted to assess how well machine learning models can predict popularity and whether those predictions align with public sentiment.

## Data Analysis:
From the boxplots I created, it was clear that Billie Eilish, Sabrina Carpenter, and Charli XCX had higher median popularity than Beyoncé. Billie’s songs were particularly consistent, with tight, high popularity scores, while Beyoncé’s tracks were more varied and generally lower in comparison. A t-test confirmed that Beyoncé’s average popularity was significantly lower than Billie’s (p < 0.0001), raising questions about how closely critical acclaim reflects listener response.
Further t-tests showed that energy was the most distinguishing feature among pop artists. Billie Eilish had a significantly lower energy profile than both Sabrina Carpenter and Chappell Roan, reinforcing her reputation for more subdued, atmospheric music. Taylor Swift’s album leaned toward a similarly mellow tone, also placing her below the energy levels of Sabrina and Chappell.
I also found that speechiness was a key stylistic differentiator. Beyoncé’s tracks had significantly higher speechiness (p = 0.0175), consistent with her narrative-driven and spoken-word content. Other features like danceability, tempo, and instrumentalness showed no statistically significant differences, suggesting some stylistic overlap among the artists.
Wanting to understand what actually drives popularity, I applied multiple linear regression and found that danceability, acousticness, and liveness were significant predictors—tracks that were more danceable and less acoustic or “live”-sounding tended to perform better. However, the regression model had moderate predictive power (R² = 0.36), so I turned to machine learning.
My Random Forest model yielded an R² of 0.34, identifying energy, danceability, and loudness as top predictors. XGBoost slightly improved that fit (R² = 0.36) and ranked loudness, liveness, and acousticness as the most important factors. Both models confirmed that sonically polished, energetic songs with studio-quality production tend to achieve higher popularity.
To visualize feature interactions, I also built a decision tree. One key takeaway was that songs with higher loudness, lower acousticness, and moderate energy were predicted to be the most popular—once again reinforcing that high-energy, high-production tracks are more appealing to listeners than soft or live-sounding ones.

## Findings:
- Billie Eilish’s songs are significantly more popular than Beyoncé’s.
- Sabrina Carpenter and Charli XCX also had higher median popularity than Beyoncé.
- Beyoncé stands out for her high speechiness and narrative-driven style, but this doesn’t translate into higher streaming popularity.
- The decision tree showed that songs with higher loudness, lower acousticness, and moderate energy tend to be more popular.
- Regression, Random Forest, and XGBoost all confirmed that loud, energetic, and less “live” sounding tracks are more popular.
- Beyoncé’s winning album did not align most closely with the traits that statistically drive popularity.

## Options Considered:
- Limiting the analysis to only two artists or comparing full discographies instead of just nominated albums
- Expanding the model with lyrical sentiment analysis or other NLP methods
- Comparing Grammy data across multiple years (though I limited this project to 2025)

## Recommendations:
This analysis highlights a disconnect between Grammy recognition and measurable listener impact. While the Recording Academy may prioritize artistry, cohesion, or cultural relevance, my findings suggest that several other artists—most notably Billie Eilish, Sabrina Carpenter, and Charli XCX—released albums that better aligned with what listeners value. If future awards were to incorporate both creative merit and audience reception through data, they could better reflect the full spectrum of musical success.
