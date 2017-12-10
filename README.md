# #6 Code for the delete student action
Code shown and explained in teachings    

<img src="/img/delete.png" width="600px" />    

### Code added to the controller
````java 
  ArrayList<Student> students = new ArraList<>();
  
  @GetMapping("/delete")
  public String delete(@RequestParam("id") int id, Model model) {
        model.addAttribute("student", students.get(id));
        return "delete";
  }         
  
  @PostMapping("/delete")
  public String delete(@ModelAttribute Student student){
        students.remove(student.getStudentId());
        return "redirect:/";
  }

````   
### delete.html
````java    
    <h2>Are you sure you want to delete</h2>
    
    <form action="#" th:action="@{/delete}"  method="post" >
        <p th:text="${student.firstName + ' ' +  student.lastName}"></p>
        <input type="hidden"  th:field="${student.studentId}"  />
        <input type="submit" value="YES" class="btn btn-del w"/>
        <a href="/" class="btn btn-create w" >NO</a>
    </form>
```` 


<div align="right">&copy; clbo@kea.dk</div>
