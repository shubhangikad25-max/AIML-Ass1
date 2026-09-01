/*------------------------------------------------
   Vacuum Cleaner Intelligent Agent
-------------------------------------------------*/

:- dynamic dirty/1.
:- dynamic vacuum_location/1.

/*---------- Knowledge Base ----------*/

/* Rooms */
room(a).
room(b).
room(c).

/* Movement Path */
next_room(a, b).
next_room(b, c).

/* Dirty Rooms */
dirty(a).
dirty(c).

/* Initial Vacuum Location */
vacuum_location(a).


/*---------- Inference Engine ----------*/

/* Rule 1: If no dirt remains -> STOP */
action(stop) :-
    \+ dirty(_).

/* Rule 2: If current room is dirty -> CLEAN */
action(clean) :-
    vacuum_location(Room),
    dirty(Room).

/* Rule 3: Move to the next room */
action(move(ToRoom)) :-
    vacuum_location(CurrentRoom),
    next_room(CurrentRoom, ToRoom).


/*---------- Perform Actions ----------*/

/* Perform Cleaning */
perform(clean) :-
    vacuum_location(Room),
    retract(dirty(Room)),
    format("Vacuum cleaned room ~w.~n", [Room]).

/* Perform Movement */
perform(move(ToRoom)) :-
    retract(vacuum_location(_)),
    assert(vacuum_location(ToRoom)),
    format("Vacuum moved to room ~w.~n", [ToRoom]).

/* Perform Stop */
perform(stop) :-
    format("All rooms are clean. Stopping...~n", []).


/*---------- Control Loop ----------*/

start :-
    action(Action),
    format("Selected Action: ~w~n", [Action]),
    perform(Action),
    (
        Action = stop
        ->
        !
        ;
        start
    ).
