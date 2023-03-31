# checkpoint_procedural_algorithm
// task 1
function dot_product(v1, v2) {
  let ps = 0;
  for (let i = 0; i < v1.length; i++) {
    ps += v1[i] * v2[i];
  }
  return ps;
}


function determine_orthogonality(vectors) {
  let orthogonal = [];
  for (let i = 0; i < vectors.length; i+=2) {
    let v1 = vectors[i];
    let v2 = vectors[i+1];
    let dotProd = dot_product(v1, v2);
    if (dotProd === 0) {
      orthogonal.push(true);
    } else {
      orthogonal.push(false);
    }
  }
  return orthogonal;
}


let vectors = [[1, 2, 3], [-1, 0, 1], [2, -1, 0], [0, 4, -2]];
let isOrthogonal = determine_orthogonality(vectors);
console.log(isOrthogonal);

// task 2
function insertionSort(arr) {
  for (let i = 1; i < arr.length; i++) {
    let key = arr[i];
    let j = i - 1;
    while (j >= 0 && arr[j] > key) {
      arr[j + 1] = arr[j];
      j--;
    }
    arr[j + 1] = key;
  }
  return arr;
}
