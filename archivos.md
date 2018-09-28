# Trabajo con archivos

#### Leer un archivo linea

````go
func main() {
    file, err := os.Open("/path/to/file.txt")
    if err != nil {
        log.Fatal(err)
    }
    defer file.Close()

    scanner := bufio.NewScanner(file)
    for scanner.Scan() {
        fmt.Println(scanner.Text())
    }

    if err := scanner.Err(); err != nil {
        log.Fatal(err)
    }
}
````

#### Leer un archivo completo a un string

````go
func main() {
    dat, err := ioutil.ReadFile("/tmp/dat")
    if err != nil {
        log.Fatal(err)
    }
    fmt.Print(string(dat))
}
````
