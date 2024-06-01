# SOUND

To generate sound through the speaker.

## Syntax

`SOUND freq,duration`

## Comments

*freq* is the desired frequency in Hertz (cycles per second). *freq* is a numeric expression within the range of 37 to 32767.

*duration* is the desired duration in clock ticks. Clock ticks occur 18.2 times per second. *duration* must be a numeric expression within the range of 0 to 65535.

Values below .022 produce an infinite sound until the next `SOUND` or [PLAY](PLAY) statement is executed.

If *duration* is zero, any active `SOUND` statement is turned off. If no `SOUND` statement is running, a duration of zero has no effect.

The sound is executed in foreground or background depending on the [PLAY](PLAY) statement.

## Examples

The following example creates random sounds of short duration:

```vb
2500 SOUND RND*1000+37, 2
2600 GOTO 2500
```

The following table shows the relationship of notes and their frequencies in the two octaves adjacent to middle C.

**Table 5**

Relationships of Notes and Frequencies

| Note | Frequency | Note | Frequency |
| ---- | --------- | ---- | --------- |
| C    | 130.810   | C*   | 523.250 |
| D    | 146.830   | D    | 587.330 |
| E    | 164.810   | E    | 659.260 |
| F    | 174.610   | F    | 698.460 |
| G    | 196.000   | G    | 783.990 |
| A    | 220.000   | A    | 880.000 |
| B    | 246.940   | B    | 987.770 |
| C    | 261.630   | C    | 1046.500 |
| D    | 293.660   | D    | 1174.700 |
| E    | 329.630   | E    | 1318.500 |
| F    | 349.230   | F    | 1396.900 |
| G    | 392.000   | G    | 1568.000 |
| A    | 440.000   | A    | 1760.000 |
| B    | 493.880   | B    | 1975.500 |

**Middle C.*

By doubling or halving the frequency, the coinciding note values can be estimated for the preceding and following octaves.

To produce periods of silence, use the following statement:

```VB
SOUND 32767, duration
```

To calculate the duration of one beat, divide beats per minute into the number of clock ticks in a minute (1092).

The following table illustrates tempos requested by clock ticks:

**Table 6**

Tempos Requested by Clock Ticks

| Tempo     | Notation    | Beats/Minute | Ticks/Beat  |
| --------- | ----------- | ------------ | ----------- |
| very slow | Larghissimo |              |             |
|           | Largo       | 40-66        | 27.3-18.2   |
|           | Larghetto   | 60-66        | 18.2-16.55  |
|           | Grave       |              |             |
|           | Lento       |              |             |
|           | Adagio      | 66-76        | 16.55-14.37 |
| slow      | Adagietto   |              |             |
|           | Andante     | 76-108       | 14.37-10.11 |
| medium    | Andantino   |              |             |
|           | Moderato    | 108-120      | 10.11-9.1   |
| fast      | Allegretto  |              |             |
|           | Allegro     | 120-168      | 9.1-6.5     |
|           | Vivace      |              |             |
|           | Veloce      |              |             |
|           | Presto      | 168-208      | 6.5-5.25    |
| very fast | Prestissimo |              |             |
