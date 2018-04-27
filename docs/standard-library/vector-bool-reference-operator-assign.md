---
title: vector&lt;bool&gt;::reference::operator= | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- =
- operator=
- vector<bool>::reference::operator=
- std::vector<bool>::reference::operator=
dev_langs:
- C++
helpviewer_keywords:
- = operator, with specific C++ Standard Library objects
- reference::operator=
ms.assetid: eed20d81-36b9-40b2-a3b6-340ed0bb4f34
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e44ccfee5199573a2076366c9ae36287230e6a49
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="vectorltboolgtreferenceoperator"></a>vector&lt;bool&gt;::reference::operator=

Bir bite bir Boolean değeri, veya başvurulan bir öğenin tuttuğu değeri atar.

## <a name="syntax"></a>Sözdizimi

```cpp
reference& operator=(const reference& Right);

reference& operator=(bool Val);
```

### <a name="parameters"></a>Parametreler

`Right` Değeri için bit atanmış olan öğe başvurusu.

`Val` Bit atanacak Boole değeri.

## <a name="example"></a>Örnek

```cpp
// vector_bool_ref_op_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    print("The vector is: ", vb);

    // Invoke vector<bool>::reference::operator=()
    vector<bool>::reference refelem1 = vb[0];
    vector<bool>::reference refelem2 = vb[1];
    vector<bool>::reference refelem3 = vb[2];

    bool b1 = refelem1;
    bool b2 = refelem2;
    bool b3 = refelem3;
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;
    cout << endl;

    refelem2 = refelem1;

    print("The vector after assigning refelem1 to refelem2 is now: ", vb);

    refelem3 = true;

    print("The vector after assigning false to refelem1 is now: ", vb);

    // The initial values are still stored in the bool variables and remained unchanged
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;
    cout << endl;
}

```

## <a name="output"></a>Çıkış

```Output
The vector is: true false false true true
The original value of the 1st element stored in a bool: true
The original value of the 2nd element stored in a bool: false
The original value of the 3rd element stored in a bool: false

The vector after assigning refelem1 to refelem2 is now: true true false true true
The vector after assigning false to refelem1 is now: true true true true true
The original value of the 1st element still stored in a bool: true
The original value of the 2nd element still stored in a bool: false
The original value of the 3rd element still stored in a bool: false
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<vektör >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[vektör\<bool >:: sınıfı başvurusu](../standard-library/vector-bool-reference-class.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
