# Prompt Engineering
Prompt engineering is a new and exciting skill focused on how to better understand
and apply generative models to your tasks and use cases. Effective prompt engineer‐
ing helps you get the most out of your generative AI models and applications.
The input that you send into a generative model is typically called the prompt. The
prompt can include text for large language models, or other modalities, such as
images, video, for multimodal models. This prompt is passed to the model during
inference time to generate a “completion.”

Here is a simple example question-answer prompt and completion.

Prompt:

Who won the 2016 baseball World Series?

Completion:

The Chicago Cubs won the 2016 baseball World Series, defeating the Cleveland 
Indians in a thrilling seven-game series. It was the Cubs' first World Series 
title in 108 years, ending the longest championship drought in Major League 
Baseball history.

# Prompt Structure
The prompt structure used in the previous example is a simple chat-assistant struc‐
ture. A more complete prompt structure usually includes a section for each of the
following: instruction, context, input data, and output indicator


Let’s discuss the two additional prompt elements, instruction and context

# Instruction
An instruction is a piece of text that you pass to the model that describes the task you
want the model to perform. For example, you can add an instruction to our previous
example to guide the model to generate a one-sentence summary.

Prompt:
User: Answer the following question in one sentence.(instruction) 

Who won the 2016 baseball World Series?

Completion:

Assistant: 
The Chicago Cubs won the 2016 baseball World Series, defeating the 
Cleveland Indians in a thrilling seven-game series that ended with a final 
score of 8-7 in extra innings.

And indeed, the model responded with a single sentence.

Writing effective instructions for generative AI models involves clarity, specificity,
and context to guide the model toward the desired output. Instructions should be
straightforward and easy to understand. The more specific your instruction, the
better the model can fulfill your request. Providing relevant context can help the
model better understand the task or topic at hand.

# Context
Context refers to relevant information or details that you pass to the model, so it
better understands the task or topic and responds appropriately. This context can
include preceding dialogue, background information, specific user requests, or any
data that provides a frame of reference for the model to generate more contextually
relevant and accurate responses. Passing context allows for more coherent and mean‐
ingful interactions with the model.

 Instruction

User: Answer the question using the format shown in the context.

Context

Who won the baseball World Series in 2022?

The Houston Astros won the World Series in 2022. They defeated the Philadelphia 
Phillies.
 
Who won the baseball World Series in 2021?

The Atlanta Braves won the World Series in 2021. They defeated the Houston Astros.
 
Who won the baseball World Series in 2020?

The Los Angeles Dodgers won the World Series in 2020. They defeated the Tampa Bay 
Rays.

Input data and output indicator

Who won the baseball World Series in 2016?

Assistant:

The Chicago Cubs won the World Series in 2016. They defeated the Cleveland 
Indians.


You can see how the model learned from the examples in the context and generated a
completion in the desired format. Specifically, the assistant responded with a succinct
answer that does not include extra details such as the final score of the baseball
game—or the number of games in the series, as in the previous example


Let’s look at examples of zero-shot, one-shot, and few-shot inference to help you
visualize their differences in both prompt context and model response


# Zero-Shot Inference
Here’s an example using zero prompts in the context.

Prompt:

User: Who won the 2016 baseball World Series?

Completion:

Assistant: The Chicago Cubs won the 2016 baseball World Series, defeating the 
Cleveland Indians in a thrilling seven-game series. It was the Cubs' first 
World Series title in 108 years, ending the longest championship drought in 
Major League Baseball history.

The zero-shot completion still includes additional information, because the model
didn’t have any example to follow

# One-Shot Inference
The following example adds an instruction and one-shot prompt in the context.

Prompt:

User: Answer the question using the format shown in the context.
Who won the baseball World Series in 2022?
The Houston Astros won the World Series in 2022. They defeated the Philadelphia 
Phillies.

Who won the 2016 baseball World Series?

Assistant:

Completion:

The 2016 World Series was won by the Chicago Cubs. They defeated the Cleveland 
Indians in seven games, becoming the first team to win the World Series after a 
108-year drought.

The one-shot completion is closer to our desired output but still has a little bit too
much detail.

# Few-Shot Inference

The following example shows what happens if you add few-shot prompt in the
context.

Prompt:

User: Answer the question using the format shown in the context.

Who won the baseball World Series in 2022?

The Houston Astros won the World Series in 2022. They defeated the Philadelphia 
Phillies.
 
Who won the baseball World Series in 2021?

The Atlanta Braves won the World Series in 2021. They defeated the Houston 
Astros.
 
Who won the baseball World Series in 2020?

The Los Angeles Dodgers won the World Series in 2020. They defeated the Tampa 
Bay Rays.

Who won the 2016 baseball World Series?

Assistant:

Completion:
The Chicago Cubs won the World Series in 2016. They defeated the Cleveland 
Indians.

Note how the model generates a more focused and relevant response for just that
request as you add more in-context examples called “shots.


There are subtle differences between the zero-shot, one-shot, and few-shot comple‐
tions. With more examples, or shots, the model more closely follows the pattern of
the response of the in-context prompt-completion pairs.
