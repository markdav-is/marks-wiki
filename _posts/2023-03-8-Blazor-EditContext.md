---
title: Blazor EditContext Validations and ViewModels
date: 2023-02-28
---

# Blazor has a simple model for form Validation

- Blazor provides a set of input components that handle binding field data to a model and validating the user input when the form is submitted.
- The EditForm component wraps these input components and orchestrates the validation process through an EditContext.
- The EditContext is an object that tracks the state of a model object that is being edited by a form. It also exposes methods to validate the model manually or automatically.
- The validation logic for the model can be defined using data annotations attributes or custom validators that are compatible with the EditForm and EditContext.

# Mysterious ways of the EditContext<Model> and edit forms
We are talking about html forms here.  Using the EditForm Blazor component will render a form tag.  Other UI Frameworks like Blazorise have a Validations component that wraps a set of validators aka a form tag.  Both of these components expose a Model parameter as the most common way to hook into the validation.  What you don't see (but it's there) is the EditContext<Model> that's created to facilitate this orchestration.  Knowing it's there can be very useful.  It's the EditContext that is passed to every child component on the form as a Cascading Parameter.  You can access it in your custom components if you like, and all the control vendors access it as well to play nicely with the validation cycle. 

# It's tricky when things get complicated, ViewModels are your friends
A simple form with a simple model make it easy to see how the Model is validated. Set the Model property on the form, and away you go.  But what happens when you have many models?  In this situation, it's a great idea to create a ViewModel.  Even if you just use it on the page to coordinate the validation.  Let's use ClassRoom/Student/Quiz/Questions as an example.  If you have bits that editable on all three models, you could have three forms, _or_ you can have one form and declare a ViewModel like so:

``` 
class QuizViewModel{
    public ClassRoom ClassRoom {get; set;}
    public Student Student {get; set;}
    public Quiz Quiz {get; set;}
    public List<Question> Questions {get;set}
} 
```
Now you are back to having one model as far as the edit form is concerned.  So you can set EditForm.Model = quizViewModel (or Validators.Model = quizVieModel in the case of Blazorise) and then add and number of child components to handle the data fields and validation and they should all participate in the same form.


# Useful Links

- [Forms and validation Microsoft Learn.](https://learn.microsoft.com/en-us/dotnet/architecture/blazor-for-web-forms-developers/forms-validation)
- [ASP.NET Core Blazor forms and input components.](https://learn.microsoft.com/en-us/aspnet/core/blazor/forms-and-input-components?view=aspnetcore-7.0)
- [How do you manually trigger the form validation in Blazor?](https://www.syncfusion.com/faq/blazor/forms-and-validation/how-do-you-manually-trigger-the-form-validation-in-blazor)
- [How to properly manipulate validation messages in EditContext with ....](https://stackoverflow.com/questions/61892999/how-to-properly-manipulate-validation-messages-in-editcontext-with-blazor-server)

