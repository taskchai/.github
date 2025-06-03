TaskChai is a lightweight but slightly opinionated framework for defining and running multi-step workflows. It allows you to create specialized tasks and chain them together to accomplish complex objectives.

The framework is built around the idea of **Tasks** with dependencies.

A `Task` defines a unit of work that can be executed. They can be chained together to create complex workflows. Here's how to define a collection of tasks and run it:


```typescript

// Example of a simple task with a prompt
const getGardeningAdvice = T("You are a gardening expert. Suggest a watering schedule for tomatoes in a sunny location.");

// Example of a task executing a function
const getWeatherReport = T(() => fetchWeatherForLocation("my_zip_code"));

// Example of chaining tasks
const complexGardeningPlan = getWeatherReport
  .then(weatherData => T(`Based on this weather: ${JSON.stringify(weatherData)}, advise on tomato care.`))
  .then(gardeningAdvice => T(`Format this advice for a beginner: ${gardeningAdvice}`));

// To run a task:
const result = await complexGardeningPlan.run();
```
