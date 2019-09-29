<script>
  import Info from "./Info.svelte";
  import Cta from "./Cta.svelte";
  import Picture from "./Picture.svelte";

  const nav = ["home", "explore", "about"];

  export const countries = [
    {
      id: 1,
      title: "Oslo",
      content:
        "Oslo, the capital of Norway, sits on the country’s southern coast at the head of the Oslofjord. It’s known for its green spaces and museums. Many of these are on the Bygdøy Peninsula, including the waterside Norwegian Maritime Museum and the Viking Ship Museum, with Viking ships from the 9th century.",
      population: "658,390",
      land: "454.08 km2",
      established: "1048",
      image:
        "https://images.unsplash.com/photo-1516630294856-68665df1db49?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1620&q=80",
      alt: "Oslo",
      instagram: ""
    },
    {
      id: 2,
      title: "Copenhagen",
      content:
        "Copenhagen, Denmark’s capital, sits on the coastal islands of Zealand and Amager. It’s linked to Malmo in southern Sweden by the Öresund Bridge. Indre By, the city's historic center, contains Frederiksstaden, an 18th-century rococo district, home to the royal family’s Amalienborg Palace.",
      population: "777,218",
      land: "292.5 km2",
      established: "",
      image:
        "https://images.unsplash.com/photo-1521240104483-b3e91583366c?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80",
      alt: "Copenhagen",
      instagram: ""
    },
    {
      id: 3,
      title: "Stockholm",
      content:
        "Stockholm, the capital of Sweden, encompasses 14 islands and more than 50 bridges on an extensive Baltic Sea archipelago. The cobblestone streets and ochre-colored buildings of Gamla Stan (the old town) are home to the 13th-century Storkyrkan Cathedral, the Kungliga Slottet Royal Palace and the Nobel Museum, which focuses on the Nobel Prize.",
      population: "965,232",
      land: "381.63 km2",
      established: "",
      image:
        "https://images.unsplash.com/photo-1509356843151-3e7d96241e11?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80",
      alt: "Stockholm",
      instagram: ""
    },
    {
      id: 4,
      title: "Malmo",
      content:
        "Malmö is a coastal city in southern Sweden. It lies at the eastern end of the striking Öresund Bridge, a long road and railway bridge–tunnel running to Copenhagen, Denmark. In the city center, Lilla Torg is a cobblestone square with cafes, half-timbered houses and shops selling local handicrafts.",
      population: "316,588",
      land: "156.9 km2",
      established: "",
      image:
        "https://images.unsplash.com/photo-1566886080421-16f6a741af4c?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2571&q=80",
      alt: "Malmo",
      instagram: ""
    }
  ];

  export const numberOfCities = countries.length;

  const FIRST_ITEM = 1;

  let index = 1;

  let currentCity = countries[0];

  let isNextButtonDisabled = false;

  let isPreviousButtonDisabled = true;

  $: isPreviousButtonDisabled = index <= FIRST_ITEM ? true : false;

  $: isNextButtonDisabled = index >= numberOfCities ? true : false;

  const handleNext = e => {
    index = e.detail.index;
    index = index + 1;
    currentCity = countries.find(country => country.id === index);
  };

  const handlePrevious = e => {
    index = e.detail.index;
    index = index - 1;
    currentCity = countries.find(country => country.id === index);
  };
</script>

<style>
  :global(body) {
    width: 100vw;
    height: 100vh;
    margin: 0;
  }

  main {
    width: 100vw;
    height: 100vh;
    display: flex;
    font-family: Helvetica, Arial, Sans-Serif;
  }
</style>

<main>
	<Info
    {nav}
    {...currentCity}
  />
  <Picture {...currentCity} />
  <Cta
    {index}
    {...currentCity}
    {isNextButtonDisabled}
    {isPreviousButtonDisabled}
    on:decrement={handlePrevious}
    on:increment={handleNext}
  />
</main>