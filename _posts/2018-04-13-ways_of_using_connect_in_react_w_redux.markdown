---
layout: post
title:      "Ways of using connect() in React w/Redux"
date:       2018-04-13 23:13:02 +0000
permalink:  ways_of_using_connect_in_react_w_redux
---


There are multiple ways to connect your components to the React store and pass in the mapStateToProps and mapDispatchToProps arguments. Below is an illustration on how to handle the submit action of you form in React with Redux.

Within our form, we add a 'handleOnChange' event to each input. The function will take the value that is being input into the form fields and save it into a new Idea object, called currentIdeaForm. We then call the 'updateIdeaForm' with the data from the current form passed in. This is an action that was imported from our actions folder. 

```
handleOnChange = event => {
    const { name, value } = event.target;
    const currentIdeaForm =
      Object.assign({}, this.props.ideaForm, { [name]: value })
    this.props.updateIdeaForm(currentIdeaForm)
  }
```

For our 'handleOnSubmit' function, we call the createIdea function that was imported from our actions folder and pass in the data from the state of the current ideaForm.

```
handleOnSubmit = event => {
    event.preventDefault()
    const {  createIdea, history } = this.props;
    createIdea(this.props.ideaForm);
    history.push('/ideas')
  }
```

The reason we are able to use our action functions updateIdeaForm and createIdea on our this.props object is because of the way the mapStateToProps and the connect functions are set up. Instead of using mapDispatchToProps and bindActionCreators, we are passing in the  updateIdeaForm and createIdea into our connect function:

```
const mapStateToProps = state => {
  return {
    ideaForm: state.ideaForm
  }
}
 export default connect(mapStateToProps, { updateIdeaForm, createIdea })(IdeaForm);

```

This gives us access to this.props.updateIdeaForm and this.props.createIdea. And is a shortcut to writting something like this:
```
const mapStateToProps = state => {
  return {
    ideaForm: state.ideaForm
  }
}

const mapDispatchToProps = dispatch => {
  return bindActionCreators({updateIdeaForm, createIdea}, dispatch);
}

export default connect(mapStateToProps, mapDispatchToProps)(IdeaForm);

```

As a reminder the difference between the two function is that:
* mapStateToProps - allows us to give our component access to a specific part of the state
* mapDispatchToProps - allows us to pass through our action creator as a prop

