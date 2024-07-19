## Types of class loaders

I've given an overview of the three main types of class loaders. In this section, we'll go over each one in more detail. To start, take a look at this diagram of Java class loaders interacting in a Java program.

![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAYAAACNiR0NAAAABGdBTUEAALGPC/xhBQAAACBjSFJNAAB6JgAAgIQAAPoAAACA6AAAdTAAAOpgAAA6mAAAF3CculE8AAAACXBIWXMAAA3XAAAN1wFCKJt4AAABWWlUWHRYTUw6Y29tLmFkb2JlLnhtcAAAAAAAPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iWE1QIENvcmUgNS40LjAiPgogICA8cmRmOlJERiB4bWxuczpyZGY9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkvMDIvMjItcmRmLXN5bnRheC1ucyMiPgogICAgICA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIgogICAgICAgICAgICB4bWxuczp0aWZmPSJodHRwOi8vbnMuYWRvYmUuY29tL3RpZmYvMS4wLyI+CiAgICAgICAgIDx0aWZmOk9yaWVudGF0aW9uPjE8L3RpZmY6T3JpZW50YXRpb24+CiAgICAgIDwvcmRmOkRlc2NyaXB0aW9uPgogICA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgpMwidZAAABOklEQVQ4Ea2V3U7DMAxGV8QN3OyBB+oDdK/L75DKOV0cmdC0EizSp7iJfWwvbXaY5/mIJnUoA/s+7N6cfSKe+XgoD1/ML+gpANhdaN4zBr2iC5ruCuCT+RGdWHx2bRgGk/yCuuaePsX3hPmALq4tww1kFscbWqBuYldoYxujr8O5dpeh2eEHlIAMbmHVt62g77ikvbZZKmLqdLOTfSwsk49o96eJltuWItDTt3Kl7XCvtoldYyP5GnTEMQDv2MrhWq56HRZknKsDtlV9oBjam5XFexi8285kz9WNPP+95QaWXx+h7aF0X/61w8gwA/MBjDzH6a9DcchttrB6APHj4t/1yazlQ2fh/5+emQF5BXVhqbqtbq6XAyAv1zjN3S8A3wyNu5DlhTFZ3Rl59+3CNio1VsZZ4E3/Ar4BuSbVUBIuWisAAAAASUVORK5CYII=)

![A diagram of the types of Java class loaders.](https://images.idgesg.net/images/article/2023/06/classloaders-fig1-100942398-large.jpg?auto=webp&quality=85,70)

Figure 1. Java class loaders in a Java program.

Notice that the class search begins with the bootstrap class loader. If the class is not found, the class search returns to the extension class loader for another search. If the class is still not found, the process tries again using the application class loader. If none of the searches finds the class, then the program throws a `ClassNotFoundExecption`.