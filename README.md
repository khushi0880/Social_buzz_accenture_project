# Social media & content creation data analysis
### Scenario
Social Buzz is a content creation platform. Social Buzz emphasizes content by keeping all users anonymous, only tracking user reactions on every piece of content. There are over 100 ways that users can react to content, spanning beyond the traditional reactions of likes, dislikes, and comments. This ensures that trending content, as opposed to individual users, is at the forefront of user feeds. Due to their rapid growth and digital nature of their core product, the amount of data that they create, collect and must analyze is huge. Social Buzz want to analyse their content categories that highlights the top 5 categories with the largest aggregate popularity.
## Data Sources
1. Content
2. Reactions
3. Reaction Type
## Tool
1. Excel- Data Cleaning
2. SQL- Data Analysis
## Explanatory Analysis
```SQL
SELECT 
  Content.Category,
  SUM(Reaction_type.Score) AS Aggregate_score
FROM 
  `capstone-project-cyclists.content_creation.Reactions` AS Reactions
JOIN
  `capstone-project-cyclists.content_creation.Content` AS Content
  ON Reactions.Content_ID = content.Content_ID 
JOIN
  `capstone-project-cyclists.content_creation.Reaction_type` AS Reaction_type
  ON Reactions.Reaction_Type = Reaction_type.ReactionType
GROUP BY
  Content.Category
ORDER BY
  Aggregate_score DESC
LIMIT 5
```
## Result
the top 5 categories with the largest aggregate popularity are-
1. animals - 69548
2. healthy eating - 69067
3. technology - 68521
4. science - 66549
5. culture - 64952

