# :zap: Next Tailwind Supabase

* Next frontend to display images from a Supabase PostgreSQL database
* **Note:** to open web links in a new window use: _ctrl+click on link_

![GitHub repo size](https://img.shields.io/github/repo-size/AndrewJBateman/next-tailwind-supabase?style=plastic)
![GitHub pull requests](https://img.shields.io/github/issues-pr/AndrewJBateman/next-tailwind-supabase?style=plastic)
![GitHub Repo stars](https://img.shields.io/github/stars/AndrewJBateman/next-tailwind-supabase?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/AndrewJBateman/next-tailwind-supabase?style=plastic)

## :page_facing_up: Table of contents

* [:zap: Next Tailwind Supabase](#zap-next-tailwind-supabase)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Technologies](#signal_strength-technologies)
  * [:floppy_disk: Setup](#floppy_disk-setup)
  * [:flashlight: Testing](#flashlight-testing)
  * [:computer: Code](#computer-code)
  * [:cool: Features](#cool-features)
  * [:clipboard: Status & To-Do List](#clipboard-status--to-do-list)
  * [:clap: Inspiration](#clap-inspiration)
  * [:file_folder: License](#file_folder-license)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

* Supabase is an open-source alternative to Firebase, but uses PostgreSQL instead of document database. Database is realtime & can use SQL joins. Realtime notifications via Websockets. RESTful API requires no backend code.

## :camera: Screenshots

![Example screenshot](./img/array.png)

## :signal_strength: Technologies

* [Next.js v12](https://nextjs.org/) React framework
* [React v17](https://reactjs.org/) Javascript library
* [Supabase public Beta](https://supabase.io/) Postgres database
* [supabase-js v1](https://www.npmjs.com/package/@supabase/supabase-js) isomorphic Javascript client for Supabase

## :floppy_disk: Setup

* `npm i` to install dependencies then...
* Create free account with Supabase and create table from SQL menu/User Management Starter as per [tutorial](https://www.youtube.com/watch?v=x38PWNZhSEM)
* Add data to table - I found image URLs from [Pinterest](https://www.pinterest.com.mx/) - exported as a CSV file - see `images_allRows.csv`. It is easy to import this into a new Supabase table mand set id as the PRIMARY_ID
* Create `.env.local` then add your Supabase API Authentication credentials as shown in `.env.example.local`
* `ng serve` for a dev server. Navigate to `http://localhost:4200/` - app will automatically reload if you change any of the source files
* `ng run build` for a build folder

## :flashlight: Testing

* Tests not set up

## :computer: Code

* tba

```typescript
export async function getStaticProps() {
  const supabaseAccess = createClient(
    process.env.SUPABASE_URL || '',
    process.env.SUPABASE_KEY || ''
  )

  const { data } = await supabaseAccess.from('images').select('*').order('id')
  return {
    props: {
      images: data,
    },
  }
}
```

## :cool: Features

* Supabase user interface is cool to work with and they have SQL templates to create a user login etc.

## :clipboard: Status & To-Do List

* Status: Working, deployed to Vercel
* To-Do: Nothing

## :clap: Inspiration

* [Youtube: Lee Robinson: Building an Image Gallery with Next.js, Supabase, and Tailwind CSS](https://www.youtube.com/watch?v=BSoRXk1FIw8)

## :file_folder: License

* N/A

## :envelope: Contact

* Repo created by [ABateman](https://github.com/AndrewJBateman), email: gomezbateman@yahoo.com
