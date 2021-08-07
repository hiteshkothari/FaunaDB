Create an Index to get the data that has to be deleted

For eg. I have to delete the datas where a column contains wrong data







Here is the delete FQL 



Map(
  Paginate(Match(Index("studentDummy_by_worng_studentId"), true)),
  Lambda(
    "X",
    Delete(Select(["ref"], Get(Var("X"))))
  )
)


The above query has to run several times till all the data has been deleted. It can delete max 64 documents as once.
