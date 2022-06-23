package coverage

import (
	"os"
	"reflect"
	"testing"
	"time"
)

// DO NOT EDIT THIS FUNCTION
func init() {
	content, err := os.ReadFile("students_test.go")
	if err != nil {
		panic(err)
	}
	err = os.WriteFile("autocode/students_test", content, 0644)
	if err != nil {
		panic(err)
	}
}

// WRITE YOUR CODE BELOW
func TestPeopleLen(t *testing.T) {
	var p People;
	p = append(p, Person{firstName: "John", lastName: "Doe", birthDay: time.Date(1980, 1, 1, 0, 0, 0, 0, time.Local)})
	p = append(p, Person{firstName: "Jane", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})

	want := 2
	got := p.Len()

	if got != want {
		t.Errorf("TestPeopleLen got: %v, want: %v", got, want)
	}
}

func TestPeopleLessSortByBirthDayFromYoungestToOldestMustReturnTrue(t *testing.T) {
	var p People;
	
	// Oldest person
	p = append(p, Person{firstName: "John", lastName: "Doe", birthDay: time.Date(1980, 1, 1, 0, 0, 0, 0, time.Local)})

	// Youngest person
	p = append(p, Person{firstName: "Jane", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})

	want := true
	got := p.Less(1, 0)

	if got != want {
		t.Errorf("TestPeopleLessSortByBirthDayFromYoungestToOldestMustReturnTrue got: %v, want: %v", got, want)
	}
}

func TestPeopleLessSortByBirthDayFromOldestToYoungestMustReturnFalse(t *testing.T) {
	var p People;
	
	// Oldest person
	p = append(p, Person{firstName: "John", lastName: "Doe", birthDay: time.Date(1980, 1, 1, 0, 0, 0, 0, time.Local)})

	// Youngest person
	p = append(p, Person{firstName: "Jane", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})

	want := false
	got := p.Less(0, 1)

	if got != want {
		t.Errorf("TestPeopleLessSortByBirthDayFromOldestToYoungestMustReturnFalse got: %v, want: %v", got, want)
	}
}

func TestPeopleLessEqualLastnameSortByFirstnameMustReturnTrue(t *testing.T) {
	var p People;
	
	p = append(p, Person{firstName: "John", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})
	p = append(p, Person{firstName: "Alle", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})

	want := true
	got := p.Less(1, 0)

	if got != want {
		t.Errorf("TestPeopleLessEqualLastnameSortByFirstnameMustReturnTrue got: %v, want: %v", got, want)
	}
}

func TestPeopleLessEqualLastnameSortByFirstnameMustReturnFalse(t *testing.T) {
	var p People;
	
	p = append(p, Person{firstName: "Alle", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})
	p = append(p, Person{firstName: "John", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})

	want := false
	got := p.Less(1, 0)

	if got != want {
		t.Errorf("TestPeopleLessEqualLastnameSortByFirstnameMustReturnFalse got: %v, want: %v", got, want)
	}
}

func TestPeopleLessEqualFirstnameSortByLastnameMustReturnTrue(t *testing.T) {
	var p People;
	
	p = append(p, Person{firstName: "John", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})
	p = append(p, Person{firstName: "John", lastName: "Arley", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})

	want := true
	got := p.Less(1, 0)

	if got != want {
		t.Errorf("TestPeopleLessEqualFirstnameSortByLastnameMustReturnTrue got: %v, want: %v", got, want)
	}
}

func TestPeopleLessEqualFirstnameSortByLastnameMustReturnFalse(t *testing.T) {
	var p People;
	
	p = append(p, Person{firstName: "John", lastName: "Doe", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})
	p = append(p, Person{firstName: "John", lastName: "Roy", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)})

	want := false
	got := p.Less(1, 0)

	if got != want {
		t.Errorf("TestPeopleLessEqualFirstnameSortByLastnameMustReturnFalse got: %v, want: %v", got, want)
	}
}

func TestPeopleSwap(t *testing.T) {
	var p People;
	
	person1 := Person{firstName: "John 1", lastName: "Doe 1", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)}
	person2 := Person{firstName: "John 2", lastName: "Doe 2", birthDay: time.Date(1990, 1, 1, 0, 0, 0, 0, time.Local)}

	p = append(p, person1)
	p = append(p, person2)

	want := person2
	p.Swap(0, 1)
	got := p[0]

	if !reflect.DeepEqual(got, want) {
		t.Errorf("TestPeopleSwap got: %v, want: %v", got, want)
	}
}

///////////////////////////////////////////////////////////////////////////////////////////////////////

func TestMatrixNewWithBadrowMustThrowingError(t *testing.T) {
	_, e := New("\n3 4\n5")

	if e == nil {
		t.Errorf("TestMatrixNewWithBadrowMustThrowingError error: %v", e)
	}
}

func TestMatrixNewWithAdditionalColMustThrowingError(t *testing.T) {
	_, e := New("1\n3\n5 6")

	if e == nil {
		t.Errorf("TestMatrixNewWithAdditionalColMustThrowingError error: %v", e)
	}
}

func TestMatrixNewThreeRowsTwoColumns(t *testing.T) {
	m, e := New("1 2\n3 4\n5 6")

	if e != nil {
		t.Errorf("TestMatrixNewThreeRowsTwoColumns error: %v", e)
	}

	want := [...]int{3, 2}
	got := [...]int{m.rows, m.cols}

	if got != want {
		t.Errorf("TestMatrixNewThreeRowsTwoColumns got: %v, want: %v", got, want)
	}
}

func TestMatrixGetRows(t *testing.T) {
	m, e := New("1 2\n3 4\n5 6")

	if e != nil {
		t.Errorf("TestMatrixGetRows error: %v", e)
	}

	want := [][]int {
		{1, 2},
		{3, 4},
		{5, 6},
	}

	got := m.Rows()

	if !reflect.DeepEqual(got, want) {
		t.Errorf("TestMatrixGetRows got: %v, want: %v", got, want)
	}
}

func TestMatrixGetColumns(t *testing.T) {
	m, e := New("1 2\n3 4\n5 6")

	if e != nil {
		t.Errorf("TestMatrixGetColumns error: %v", e)
	}

	want := [][]int {
		{1, 3, 5},
		{2, 4, 6},
	}

	got := m.Cols()

	if !reflect.DeepEqual(got, want) {
		t.Errorf("TestMatrixGetColumns got: %v, want: %v", got, want)
	}
}

func TestMatrixSetValidIndexMustReturnTrue(t *testing.T) {
	m, e := New("1 2\n3 4\n5 6")

	if e != nil {
		t.Errorf("TestMatrixSetValidIndexMustReturnTrue error: %v", e)
	}
	
	want := true
	got := m.Set(0, 0, 9)

	if got != want {
		t.Errorf("TestMatrixSetValidIndexMustReturnTrue got: %v, want: %v", got, want)
	}
}

func TestMatrixSetOutOfIndexMustReturnFalse(t *testing.T) {
	m, e := New("1 2\n3 4\n5 6")

	if e != nil {
		t.Errorf("TestMatrixSetOutOfIndexMustReturnFalse error: %v", e)
	}
	
	want := false
	got := m.Set(10, 15, 9)

	if got != want {
		t.Errorf("TestMatrixSetOutOfIndexMustReturnFalse got: %v, want: %v", got, want)
	}
}

func TestMatrixSet(t *testing.T) {
	want, e := New("1 2\n3 9\n8 6")
	if e != nil {
		t.Errorf("TestMatrixSet for want error: %v", e)
	}

	got, e := New("1 2\n3 4\n5 6")

	if e != nil {
		t.Errorf("TestMatrixSet for got error: %v", e)
	}

	got.Set(1, 1, 9)
	got.Set(2, 0, 8)

	if !reflect.DeepEqual(got, want) {
		t.Errorf("TestMatrixSet got: %v, want: %v", got, want)
	}
}
