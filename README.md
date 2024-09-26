# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Add your answers to this markdown file.

## Plagarism Statement

All exercises must contain the following statement:
“I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.”

## Note
I am attempting this from scratch, however I believe that I do remember our logic from last semester on the occasions when it came up after class after lecture.
Please forgive me if it is too drawn out, as I am trying to make my logic clearer with this excercise in particular.
Finally I will also check my new answers against my old answers after I complete them.

## Answer
1a)As mentioned in class, you could define your algorithm using incredably loose bounds on both the higher end and lower end, but that doesn't mean that actually gives you any useful information
about how your algorithm will actually function. Thinking about it this way, even if you have an analysis, it may be misleading by not telling you anything useful to begin with.

1b)On a simular note, the difference in constants may also be a reason for asymptotic analysis to be misleading. As was stated in lecture, we look to ignore the constants in asymptotic analysis, but in practice, we observe that they do have impacts on an algorithm, especially when looking at small amounts of input. When we look at how an algorithm performs working on very large data sets, a difference as small as say 5n and 500n might not be noticable. But when talking about smaller data sets 500 is 100* larger than just 5. On that same note, this logic also applies to the difference in terms we observe in an analysis. Take $n^10 + n^2$ if we were to analyze them, we would simplify it down to just $n^10$. While it may not seem like it, but $n^2$ still has the potential to be very large, and depending ont the data set in actual practice, this may be more or less relevent but regardless, we still may be mislead by the ignoring of constants and smaller terms.

1c)My final reason is that asymptotic analysis takes absolutely no account of the hardware it is running on. In a sense, we complete the asymptotic analysis in an ideal void, where everything operates as efficienty as possible at every possible moment. In practice though, we know this is absolutely not the case, older machines run much slower than modern ones, sometimes both types of machines might make a mistake or have mechanical issue. In these cases we would not expect the asymptotic analysis to be comepletely correct.

2a)This problem works more like a standard math problem where we know what equation is used, the answer to the equation, and are only missing one constant. 
We set this up using the what we know is the average case for a binary search tree $\Theta(log_n)$, creating a system of equation using the number of elements and the completion time which will look like:

$constant * log_2(1000$ elements $)=5$ seconds

Simplifying, ($log_2(1000)$ is a constant value), we get: 

$constant * 9.966 =5$

Then we solve for constant:

$constant = .502$

Finally, we plug it back in for our constant but using 10000 elements:

$.502 * log_2(10000$ elements $)= 6.670$

This means that it will take about 6.670 second to complete the tree of 10000 elements.

3a)One potential reason for the 100 second runtime, is that outside software might be causing issues with your search. A computer running a single search program is one thing, but a computer running 100 programs might have that search happen slower than if it were the only thing running. On that same note, if your data was coming in through a different piece of software and not just sitting in a text file, then you are at the mercy of wherever the data is stored and thus could experience a slower search.

3b)This is sort of a funny reason, but it could be human error in some fashion. More specifically I would like to mention two mistake I personally have made in the past that led to increased runtime. The first mistake was having an incorrect algorithm, someone like me may have written and run this algorithm and while it looks correct, something internally was not set up right due to the programmers mistake. The other mistake I made during cosc 2030, where I had my timer termination put in the wrong spot so the program said I had an infinite runtime. In the given example, this might also be the case, where whatever is timing the runtime is making some sort of mistake. Either of these errors might not become evident with smaller input sizes, which is because many algorithms behave much differently with smaller inputs as opposed to larger ones, in addition to most small input sizes still running relatively quickly with a speed that is indistinguishable to people. The incorrect algorithm would effect smaller input sizes, but as we went over in class, with a smaller input size, we dont notice the time difference until we scale it up in practice.

3c)Finally, the las reason I can think of would be related to hardware in some fashion. Again, that might be one or more problems. For example, as mentioned int the first question, asymptotic
complexity assumes running on the most optimal machinery that is "perfect", which is why it is not considered in the actual analysis. The increased runtime might simply be a result of running the algorithm on super simple hardware like an arduino of some sort. Other than that, the hardware, while very very seldomly, might just have had a mechanical failure of some kind. Running on suboptimal hardware is more likely, but it is not impossible that the machine failed. In either case the runtime might have increased beyond what was expected.
