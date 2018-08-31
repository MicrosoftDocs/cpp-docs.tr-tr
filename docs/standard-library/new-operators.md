---
title: '&lt;Yeni&gt; işleçler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::operator delete
- new/std::operator new
ms.assetid: d1af4b56-9a95-4c65-ab01-bf43e982c7bd
author: corob-msft
ms.author: corob
ms.openlocfilehash: 11c4f3d1c994ee7a29ee47e35881d533f8c8715a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216194"
---
# <a name="ltnewgt-operators"></a>&lt;Yeni&gt; işleçleri

||||
|-|-|-|
|[delete işleci](#op_delete)|[delete [] işleci](#op_delete_arr)|[new işleci](#op_new)|
|[new [] işleci](#op_new_arr)|

## <a name="op_delete"></a>  delete işleci

Tek nesne için depolama ayırması için ifadeyi silmenin tarafından çağrılan işlev.

```cpp
void operator delete(void* ptr) throw();

void operator delete(void *,
    void*) throw();

void operator delete(void* ptr,
    const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parametreler

*PTR* değeri olan silme işleminden geçersiz işlenmek üzere bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk işlev değerini işlemek için bir silme ifadesi tarafından çağrılır *ptr* geçersiz. Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir. Bu işlev imzası olan bir işlev tanımlayabilirsiniz. Bir değeri kabul etmek için gerekli davranıştır *ptr* diğer bir deyişle null ya da daha önceki bir çağrı tarafından döndürülen [new işleci](../standard-library/new-operators.md#op_new)(**size_t**).

Null değeri için varsayılan davranış *ptr* hiçbir şey yapma sağlamaktır. Diğer herhangi bir değerini *ptr* daha önce daha önce açıklandığı gibi bir çağrı tarafından döndürülen bir değer olmalıdır. Varsayılan davranışı NULL olmayan değer *ptr* önceki çağrı tarafından ayrılan depolamayı geri alma sağlamaktır. Hangi koşullar altında bir sonraki çağrı tarafından ayrılır kısmını veya tamamını geri kazanılan gibi depolama belirtilmeyen `operator new`(**size_t**), veya herhangi bir `calloc`( **size_t**), `malloc`( **size_t**), veya `realloc`( **void**<strong>\*</strong>, **size_t**).

İkinci işlev formun yeni bir ifadeye karşılık gelen bir yerleştirme delete ifadesi tarafından çağrılır **yeni**( **std::size_t**). Hiçbir şey yapmaz.

Üçüncü işlev, formun yeni bir ifadeye karşılık gelen bir yerleştirme delete ifadesi tarafından çağrılır **yeni**( **std::size_t**, **conststd::nothrow_t &**). Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir. Bu işlev imzası olan bir işlev tanımlayabilirsiniz. Bir değeri kabul etmek için gerekli davranıştır `ptr` diğer bir deyişle null ya da daha önceki bir çağrı tarafından döndürülen `operator new`( **size_t**). Değerlendirmek için varsayılan davranıştır **Sil**(`ptr`).

### <a name="example"></a>Örnek

Bkz: [new işleci](../standard-library/new-operators.md#op_new) kullanan bir örnek **delete işleci**.

## <a name="op_delete_arr"></a>  delete [] işleci

Bir nesne dizisi için depolama ayırması için ifadeyi silmenin tarafından çağrılan işlev.

```cpp
void operator delete[](void* ptr) throw();

void operator delete[](void *,
    void*) throw();

void operator delete[](void* ptr,
    const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parametreler

*PTR* değeri olan silme işleminden geçersiz işlenmek üzere bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk işlev çağıran bir `delete[]` değerini işlemek için ifade *ptr* geçersiz. Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir. Bu işlev imzası olan bir fonksiyon tanımlayın çünkü değiştirilebilir bir işlevdir. Bir değeri kabul etmek için gerekli davranıştır *ptr* diğer bir deyişle null ya da daha önceki bir çağrı tarafından döndürülen [new işleci&#91;&#93;](../standard-library/new-operators.md#op_new_arr)(**size_t**). Null değeri için varsayılan davranış *ptr* hiçbir şey yapma sağlamaktır. Diğer herhangi bir değerini *ptr* daha önce daha önce açıklandığı gibi bir çağrı tarafından döndürülen bir değer olmalıdır. Böyle bir null olmayan değer için varsayılan davranış *ptr* önceki çağrı tarafından ayrılan depolamayı geri alma sağlamaktır. Hangi koşullar altında bir sonraki çağrı tarafından ayrılır kısmını veya tamamını geri kazanılan gibi depolama belirtilmeyen [new işleci](../standard-library/new-operators.md#op_new)(**size_t**), veya herhangi bir `calloc`(**size_t**), `malloc`(**size_t**), veya `realloc`( **void**<strong>\*</strong>, **size_t**) .

İkinci işlevi tarafından bir yerleştirme denir `delete[]` ifade karşılık gelen bir `new[]` biçiminde ifade `new[]`(**std::size_t**). Hiçbir şey yapmaz.

Üçüncü işlevi bir yerleştirme delete deyimi karşılık gelen tarafından adlandırılan bir `new[]` biçiminde ifade `new[]`( **std::size_t**, **const std::nothrow_t &**). Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir. Bu işlev imzası olan bir işlev tanımlayabilirsiniz. Bir değeri kabul etmek için gerekli davranıştır *ptr* diğer bir deyişle null ya da işleç önceki bir çağrı tarafından döndürülen `new[]`(**size_t**). Değerlendirmek için varsayılan davranıştır `delete[]`( `ptr`).

### <a name="example"></a>Örnek

Bkz: [new işleci&#91; &#93; ](../standard-library/new-operators.md#op_new_arr) kullanımı örnekleri için `operator delete[]`.

## <a name="op_new"></a>  new işleci

Yeni-tek tek nesneler için ayrılacak ifadesi tarafından çağrılan işlev.

```cpp
void* operator new(std::size_t count) throw(bad_alloc);

void* operator new(std::size_t count,
    const std::nothrow_t&) throw();

void* operator new(std::size_t count,
    void* ptr) throw();
```

### <a name="parameters"></a>Parametreler

*sayısı* depolama ayrılacak bayt sayısı.

*PTR* döndürülmesi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Düşük bayt adresi yeni ayrılan depolama alanı için bir işaretçi. Veya *ptr*.

### <a name="remarks"></a>Açıklamalar

İlk işlev ayırmak için yeni bir ifade tarafından çağrılır `count` depolama baytı uygun şekilde hizalanmış, boyutta herhangi bir nesne temsil etmek için. Program, alternatif bir işlev C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir ve bu nedenle değiştirilebilir, bu işlev imzası ile tanımlayabilirsiniz.

Gerekli depolama istendiği yalnızca ayrılabilen ise NULL olmayan bir işaretçi döndürülecek davranıştır. Her tür ayırma bir işaretçi diğer ayrılmış depolama alanından depolama ayrık verir. Contiguity birbirini izleyen çağrılar tarafından ayrılmış depolama ve sırası belirtilmez. İlk depolanan değeri belirtilmemiş. Ayrılan depolama alanını başlatma (en düşük bayt adresi) döndürülen işaretçi işaret eder. Döndürülen değer sayısı sıfır ise, işlev tarafından döndürülen değere eşit karşılaştırmaz.

Bir döngü yürütmek için varsayılan davranıştır. Döngü içinde işlev ilk istenen depolama ayırmaya çalışır. Girişimini bir çağrı içerir olmadığını `malloc`( **size_t**) belirtilmedi. Girişim başarılı olursa, işlev için ayrılan depolama alanını bir işaretçi döndürür. Aksi halde, işlev belirlenmiş çağırır [yeni işleyici](../standard-library/new-typedefs.md#new_handler). Çağrılan işlev döndürürse, döngü tekrarlanır. İstenen depolama alanı Ayır girişimi başarılı olduğunda veya çağrılan bir işlev değil döndüğünüzde döngüyü sonlandırır.

Aşağıdaki işlemlerden birini gerçekleştirmek için gerekli yeni bir işleyici davranışını verilmiştir:

- Daha fazla depolama alanı ayırma için kullanılabilir hale getirmek ve dönün.

- Çağırın ya da **iptal** veya **çıkmak**(`int`).

- Türünde bir nesne **bad_alloc.**

Varsayılan davranışını bir [yeni işleyici](../standard-library/new-typedefs.md#new_handler) türünde bir nesne için `bad_alloc`. Bir null işaretçiyse, varsayılan yeni işleyici belirler.

Contiguity art arda çağrılar tarafından ayrılmış depolama ve sırası `operator new`(**size_t**) depolanan bir başlangıç değerleri olarak belirtilmemiş.

İkinci işlev ayrılacak yerleştirme yeni ifadesi tarafından çağrılır `count` depolama baytı uygun şekilde hizalanmış, boyutta herhangi bir nesne temsil etmek için. Program, alternatif bir işlev C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir ve bu nedenle değiştirilebilir, bu işlev imzası ile tanımlayabilirsiniz.

Döndürülecek varsayılan davranıştır `operator new`(`count`), işlev başarılı olursa. Aksi takdirde null bir işaretçi döndürür.

Üçüncü işlev tarafından bir yerleştirme denir **yeni** biçiminde ifade **yeni** ( *args*) t Burada, *args* tek nesne işaretçisinin oluşur. Bu bilinen bir adresteki bir nesneye oluşturmak için yararlı olabilir. İşlev döndürür *ptr*.

Ayrılan depolama alanı boşaltmak için **new işleci**, çağrı [delete işleci](../standard-library/new-operators.md#op_delete).

Oluşturma hakkında bilgi için veya yeni, bkz: nonthrowing davranışını [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md).

### <a name="example"></a>Örnek

```cpp
// new_op_new.cpp
// compile with: /EHsc
#include<new>
#include<iostream>

using namespace std;

class MyClass
{
public:
   MyClass( )
   {
      cout << "Construction MyClass." << this << endl;
   };

   ~MyClass( )
   {
      imember = 0; cout << "Destructing MyClass." << this << endl;
   };
   int imember;
};

int main( )
{
   // The first form of new delete
   MyClass* fPtr = new MyClass;
   delete fPtr;

   // The second form of new delete
   MyClass* fPtr2 = new( nothrow ) MyClass;
   delete fPtr2;

   // The third form of new delete
   char x[sizeof( MyClass )];
   MyClass* fPtr3 = new( &x[0] ) MyClass;
   fPtr3 -> ~MyClass();
   cout << "The address of x[0] is : " << ( void* )&x[0] << endl;
}
```

## <a name="op_new_arr"></a>  new [] işleci

Ayırma, bir nesne dizisi için ayrılacak yeni bir ifade tarafından çağrılan işlev.

```cpp
void* operator new[](std::size_t count) throw(std::bad_alloc);

void* operator new[](std::size_t count,
    const std::nothrow_t&) throw();

void* operator new[](std::size_t count,
    void* ptr) throw();
```

### <a name="parameters"></a>Parametreler

*sayısı* depolama dizi nesnesi için ayrılacak bayt sayısı.

*PTR* döndürülmesi için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Düşük bayt adresi yeni ayrılan depolama alanı için bir işaretçi. Veya *ptr*.

### <a name="remarks"></a>Açıklamalar

İlk işlev çağıran bir `new[]` ayrılacak ifade `count` bayt olarak depolama uygun şekilde hizalanmış, boyutta herhangi bir dizi nesne temsil etmek için ya da daha küçük. Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir. Bu işlev imzası olan bir işlev tanımlayabilirsiniz. Gerekli aynı davranıştır [new işleci](../standard-library/new-operators.md#op_new)(**size_t**). Döndürülecek varsayılan davranıştır `operator new`( `count`).

İkinci işlevi tarafından bir yerleştirme denir `new[]` ayrılacak ifade `count` depolama baytı uygun şekilde hizalanmış, boyutta herhangi bir dizi nesne temsil etmek için. Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir. Bu işlev imzası olan bir işlev tanımlayabilirsiniz. Döndürülecek varsayılan davranıştır **operatornew**(`count`), işlev başarılı olursa. Aksi takdirde null bir işaretçi döndürür.

Üçüncü işlev tarafından bir yerleştirme denir `new[]` biçiminde ifade **yeni** ( *args*) **T**[ **N**]. Burada, *args* tek nesne işaretçisinin oluşur. İşlev döndürür `ptr`.

Ayrılan depolama alanı boşaltmak için `operator new[]`, çağrı [delete işleci&#91;&#93;](../standard-library/new-operators.md#op_delete_arr).

Oluşturma hakkında bilgi için veya yeni, bkz: nonthrowing davranışını [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md).

### <a name="example"></a>Örnek

```cpp
// new_op_alloc.cpp
// compile with: /EHsc
#include <new>
#include <iostream>

using namespace std;

class MyClass {
public:
   MyClass() {
      cout << "Construction MyClass." << this << endl;
   };

   ~MyClass() {
      imember = 0; cout << "Destructing MyClass." << this << endl;
      };
   int imember;
};

int main() {
   // The first form of new delete
   MyClass* fPtr = new MyClass[2];
   delete[ ] fPtr;

   // The second form of new delete
   char x[2 * sizeof( MyClass ) + sizeof(int)];

   MyClass* fPtr2 = new( &x[0] ) MyClass[2];
   fPtr2[1].~MyClass();
   fPtr2[0].~MyClass();
   cout << "The address of x[0] is : " << ( void* )&x[0] << endl;

   // The third form of new delete
   MyClass* fPtr3 = new( nothrow ) MyClass[2];
   delete[ ] fPtr3;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Yeni >](../standard-library/new.md)<br/>
