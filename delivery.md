# INTRODUCTION - This page is unfinished

Kanban-Zai is a collaboration process.  

Conceptually the larger team is separated into 3 teams.

* Vision team       - Responsible for constraining the over-arching path the team takes.
* Scheduling Team     - Responsible for maintaining the schedule of work.
* Execution Team    - Responsible for taking a backlog of work and creating a product.

# DESCRIPTION

## The Execution Team
Primarily comprised of developers, testers, dev ops, security advisors.

There is no measure of velocity in Kanban-Zai. The execution team takes work from the 
backlog in sized chunks.  

There is a measure of tense in Kanban-Zai.  Tense is used in the same way as it is 
normally used past tense, future tense.  At the start of a project the whole team will be working "Past Tense".  
The goal being to move to "Future Tense".

The ability of a team member to split and join cards as needed is a required part of the process.

### Consensus and breaking an impasse.
When the team votes there are 3 types of vote, yes, no and undecided. In a situation where the yes and no votes are even
then the undecided votes are no.

If there are no undecided votes 
* then the product owner may override prodcut decisions.
* the [consensus setting](https://github.com/Kanban-Zai/kanban-zai-core/blob/main/extensions/setting-consensus.md) decides the outcome


### Sprints
One week sprints are strictly enforced in Kanban-Zai.  This is because there is no velocity measure.  So instead we
use 1 week as a yard stick.  The idea is to take only what you can finish in one sprint.  Finish it an then move onto 
the next.  Biting of a little chunk at a time.  Of course in practice this requires skills that almost nobody has.  

Formally there is no expectation of commitment as there is in agile and you are not expected to finish the chunk of work
 you pickup in a week, but continually improve your card writing until you do.  The way this happens is this.  
 By using 1 week as a measure, when you get to the end of one week, take what ever work you have not completed and 
 transfer it to another card to be played next week.  Then rewrite the current card to accuratley represent what has 
 been done.  This is now what will be tested and delivered.  Repeat this process every week.
 
 Why go through all the work to write a new card?  Because it is a discipline and allows you to progress your understanding
 of the work you are doing.  If you dont like rewriting cards then write then small and only pickup what you can finish 
 in a week.  That is actually a better discipline to have.

Overtime the goal is to improve the individual and team ability to write execution cards.  The two primary areas to 
focus on when writing cards are, as in agile, value and comprehension.  In Kanban-Zai there is another factor to 
consider. "Value over time", this happens naturally in Kanban-Zai because of the 1 week sprint enforcement however
the time tense must eventually be changed to "Future tense".  At this point predictions can begin to be made about 
delivery times.  Tense is not a Kanban-Zai setting and the tense will be different on different parts of your project.
Tese just acknowledges where you are in your thinking and actions around a particular part of your project.  If your 
project is small you are likley to only refer the entire project tense, on a bigger project, different aspects will
have different tenses.  It is important to know tht predictions about delivery can only be made when you are working
in "Future Tense".

### Definition of done

# KANBAN-ZAI.YAML

## SETTINGS
   ## speed-limit: 2
   
       The amount of cards the team can work on at once.  This is  strict limit that must be adhered to.
       
   
## definition-of-done: strict
   
    When do you finish?
    
    # Predictions
    
        Determines wether or not the team will target deadlines strictly or loosley.
        
        * LOOSE - Prioritizes larger chunks of the idea for consideration and more time in the ideation phase leading to 
                  clearer goals in  the execution phase.
        * STRICT - Prioritizes smaller chunks of the idea for consideration and less time in the ideation phase but 
                  potentially longer time in the execution phase.
                  
    # cards
    
        how much time should you deliberate about cards?
        
        Types of card in Kanban-Zai
        
        * Bugs
        * Stories
        * Spikes
        * Technical Debt
        
        Values:
        1. default    - only product development work, bugs, tech debt & spikes will be handled as part of
                        the card 
        2. bugs       - Track bugs seperatley
        3. Tech Debt  - Track Tech debt and bugs seperatley
        4. spike      - Track Tech debt, bugs and spikes seperatley
        
        
    # Backlog Length
    
    Is a constraint that forces the team to maintain a backlog no longer that 
    the backlog-length setting which defaults to 12 weeks.
    
    ## card-scope: card-only
    
        Card-only | 
    ## boy-scouting
    
        Boys Scouts like to investigate.  Find problems to fix.  Because they have time on their hands.
        This can sometimes be a very helpful behaviour and sometimes it can be problematic.
        
        never | BAU only | Project only | Always
        
    ## tinkering: never
        
        Tinkering is the process of changing the codebase in off card fashion, usually as a result of boy scouting.  If 
        tinkering happends outside of the setting limits it must be reverted out of the codebase.
    
        never | BAU only | Project only | Always
    
    ## bugs: never
    
        If a bug is found mid sprint ( remembering a sprint is 1 week ) how should it be handled?  Never is the equivilent
        of a card being scheduled.  For bugs usually this would be the next sprint, but it would depend on scheduling.  
        Always implies it should be the next card someone picks up.
    
        never | BAU only | Project only | Always
         
    ## payback-tech-debt: never
       
           How much effort should be put into paying back technical debt as part of a cad this sprint?  Never in this context 
           means a card should be written about it and it should be handed off to the scheduling team.
           
           never | BAU only | Project only | Always
    
     
    ## Definition of done.
    
    It is hard to quanify a good definition of done.  It will vary from team to team.  Kanban-Zai enforces these settings 
    payback-tech-debt, card-sizing, card-scope, sprint-length to help put a tangible boundry in place.  These alone allow
    you an oobjective measure of when it is time to stop working on a card.
    
    Additionally you may add other measures.  Some good ones are...
    
    * Acceptance Criteria
    * Unit Tests
    * End to End Tests
    * Smoke tests
# Backporting   