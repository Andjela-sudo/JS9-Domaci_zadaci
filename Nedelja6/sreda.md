## Domaci zadatak za sredu do 21h

### Aplikacija TO-DO lista

* Zavrsiti na casu (12.1.2021) zapocetu aplikaziju za to-do listu koja treba da poseduje sledece funkcionalnosti:
1. Podaci iz niza se prikazuju na stranici (lista to-do itema)
2. Ima formu/input za unos novih podataka (to-do itema) u niz (automatski se azurira i prikaz na stranici)
3. Svaki item sadrzi sledece :
    - id
    - opis (desc)
    - iformaciju da li je uradjen ili ne (done)

    Na stranici za svaki item se prikazuje text - opis i checkbox polje koje menja stanje itema (uradjeno-neuradjeno), kao i  dugme za brisanje itema.
    Kada je item uradjen (done == true) tekst (desc) itema se precrta (ili se na neki drugi nacin naznaci da je item uradjen).


  Kod sa casa:
  ```
  let count = 6
const data = [
    {
        id: 1,
        desc: '1231',
        done: true
    },
    {
        id: 2,
        desc: '12312',
        done: false
    },
    {
        id: 3,
        desc: 'sdf2123',
        done: true
    },
    {
        id: 4,
        desc: 'sdfkdsfsfdsjgdg',
        done: true
    },
    {
        id: 5,
        desc: 'sdfsfsdfsdfsdfkjgdg',
        done: true
    }
]
const add = (item) => { // Напомена: објекат item садржи само desc и done (нема id)
    data.push({ id: count++, ...item })
}
const deleteById = (id) => {
    let index = data.findIndex(item => id === item.id)
    data.splice(index, 1)
}
const changeById = (id, noviItem) => {
    let index = data.findIndex(item => id === item.id)
    data.splice(index, 1, { id: id, ...noviItem })
}
export default {
    data,
    add,
    deleteById,
    changeById
}
```