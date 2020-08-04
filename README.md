# Safe Navigation operators in perl

After rolling this idea by a few people, it seems like there is
interest in adding a safe navigation operator to perl. In it's
simplest form, this is the deref operator with an added symbol to
imply that it should only happen in the referand (I think that's
the right word?) is defined. Essentially turning this

    my $safe = $ref->method;
    $safe->other_method if $safe;

into this

    $ref->method?->other_method

(notwithstanding any potential bikeshedding about what it should
look like).

After some thought, I realized two things needed to be fletched
out.

  - what exactly should happen if the referand is undefined

  - where else can this be used effectively

I would like to lay out my thoughts on this matter here.
