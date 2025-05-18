countries = ["USA", "France", "India", "Germany", "Japan","Mexico", "Canada", "Brazil", "South Africa", "Italy"]
years = [1776, 1792, 1947, 1871, 660, 1821, 1867, 1822, 1910, 1861]
leaders = ["George Washington", "Maximilien Robespierre", "Jawaharlal Nehru", "Otto von Bismarck", "Emperor Jimmu", "Agustín de Iturbide", "John A. Macdonald", "Dom Pedro I", "Louis Botha", "Victor Emmanuel II"]

def print_all():
    print("\nCountry List")
    for i in range(len(countries)):
        print(f"{i+1}. {countries[i]} | Year Formed: {years[i]} | First Leader: {leaders[i]}")

def add_item():
    country = input("Enter country name: ")
    try:
        year = int(input("Enter year of formation: "))
        leader = input("Enter first leader: ")
        countries.append(country)
        years.append(year)
        leaders.append(leader)
        print("Country added.\n")
    except ValueError:
        print("Invalid year")

def print_sorted_countries():
    print("\n Sorted Country Names")
    sorted_list = sorted(countries)
    for country in sorted_list:
        print(country)

def search_country():
    search = input("Search a Country ").strip()
    if search in countries:
        index = countries.index(search)
        print(f"\n{countries[index]} | Year Formed: {years[index]} | First Leader: {leaders[index]}")
    else:
        print("Country not found")
        
def remove_country():
    to_remove = input("Remove a country: ").strip()
    if to_remove in countries:
        index = countries.index(to_remove)
        countries.pop(index)
        years.pop(index)
        leaders.pop(index)
        print(f"{to_remove} has been removed\n")
    else:
        print("Country not found")

def menu():
    while True:
        print("1. View all countries")
        print("2. Add a country")
        print("3. View sorted country names")
        print("4. Search for a country")
        print("5. Remove a country")
        print("6. Exit")
        choice = input("Choose an option (1–6): ")

        if choice == "1":
            print_all()
        elif choice == "2":
            add_item()
        elif choice == "3":
            print_sorted_countries()
        elif choice == "4":
            search_country()
        elif choice == "5":
            remove_country()
        elif choice == "6":
            print("Goodbye!")
            break
        else:
            print("Invalid choice")

menu()
