---
title: bad_alloc Sınıfı
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: 63b474d0209a5cc385de9dc11b56d5de8382a9cf
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751537"
---
# <a name="badalloc-class"></a>bad_alloc Sınıfı

Sınıf bir ayırma isteği başarılı olmadı belirtmek için bir durum tanımlıyor.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_alloc : public exception {
    bad_alloc();
virtual ~bad_alloc();

};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what` bir uygulama tanımlı C dizesi. Üye işlevlerinin hiçbiri, tüm özel durumlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yeni >

**Namespace:** std

## <a name="example"></a>Örnek

```cpp
// bad_alloc.cpp
// compile with: /EHsc
#include<new>
#include<iostream>
using namespace std;

int main() {
   char* ptr;
   try {
      ptr = new char[(~unsigned int((int)0)/2) - 1];
      delete[] ptr;
   }
   catch( bad_alloc &ba) {
      cout << ba.what( ) << endl;
   }
}
```

## <a name="sample-output"></a>Örnek Çıktı

```Output
bad allocation
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yeni >

## <a name="see-also"></a>Ayrıca bkz.

[exception Sınıfı](../standard-library/exception-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
