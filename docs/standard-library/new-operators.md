---
title: '&lt;Yeni&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- new/std::operator delete
- new/std::operator new
ms.assetid: d1af4b56-9a95-4c65-ab01-bf43e982c7bd
caps.latest.revision: 8
manager: ghogen
ms.openlocfilehash: c993f62ef0bf65da36ba507938354877ba59d165
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltnewgt-operators"></a>&lt;Yeni&gt; işleçleri

||||
|-|-|-|
|[delete işleci](#op_delete)|[delete [] işleci](#op_delete_arr)|[new işleci](#op_new)|
|[new [] işleci](#op_new_arr)|

## <a name="op_delete"></a>  delete işleci

Tek tek nesnelerin için depolama alanı ayırması için bir silme ifadesi tarafından çağrılan işlev.

```cpp
void operator delete(void* ptr) throw();

void operator delete(void *,
    void*) throw();

void operator delete(void* ptr,
    const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parametreler

`ptr` Silme işlemi tarafından geçersiz işlenmek üzere, değeri olan işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk işlev değerini işlemek için bir silme ifadesi tarafından çağrılır `ptr` geçersiz. Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir bu işlev imzası işleviyle tanımlayabilirsiniz. Değerini kabul etmek için gerekli davranıştır `ptr` yani null ya da, önceki bir çağrı tarafından döndürülen [new işleci](../standard-library/new-operators.md#op_new)( **size_t**).

Null değeri için varsayılan davranış `ptr` hiçbir şey yapma sağlamaktır. Başka bir değer, `ptr` önceki daha önce açıklandığı gibi bir çağrı tarafından döndürülen bir değer olmalıdır. Bu tür bir NULL olmayan değer için varsayılan davranış `ptr` önceki çağrı tarafından ayrılan depolama alanını geri kazanmak için. Hangi koşullar altında bir sonraki çağrı tarafından ayrılır kısmını veya tamamını reclaimed gibi depolama belirtilmeyen `operator new`( **size_t**), ya da herhangi bir `calloc`( **size_t**), `malloc`( **size_t**), veya `realloc`( **void\***, **size_t**).

İkinci işlev formun yeni bir ifadeye karşılık gelen bir yerleştirme delete ifadesi tarafından çağrılan **yeni**( **std::size_t**). Hiçbir şey yapmaz.

Üçüncü işlev formun yeni bir ifadeye karşılık gelen bir yerleştirme delete ifadesi tarafından çağrılan **yeni**( **std::size_t**, **conststd::nothrow_t &**). Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir bu işlev imzası işleviyle tanımlayabilirsiniz. Değerini kabul etmek için gerekli davranıştır `ptr` yani null ya da, önceki bir çağrı tarafından döndürülen `operator new`( **size_t**). Değerlendirmek için varsayılan davranıştır **silmek**( `ptr`).

### <a name="example"></a>Örnek

Bkz: [new işleci](../standard-library/new-operators.md#op_new) kullanan bir örnek `operator delete`.

## <a name="op_delete_arr"></a>  delete [] işleci

Nesne dizisi için depolama alanı ayırması için bir silme ifadesi tarafından çağrılan işlev.

```cpp
void operator delete[](void* ptr) throw();

void operator delete[](void *,
    void*) throw();

void operator delete[](void* ptr,
    const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parametreler

`ptr` Silme işlemi tarafından geçersiz işlenmek üzere, değeri olan işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk işlev tarafından çağrılır bir `delete[]` değerini işlemek için ifade `ptr` geçersiz. İşlev değiştirebilen çünkü programın işlevi C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir bu işlev imzası ile tanımlayabilirsiniz. Değerini kabul etmek için gerekli davranıştır `ptr` yani null ya da, önceki bir çağrı tarafından döndürülen [new işleci&#91;&#93;](../standard-library/new-operators.md#op_new_arr)( **size_t**). Null değeri için varsayılan davranış `ptr` hiçbir şey yapma sağlamaktır. Başka bir değer, `ptr` önceki daha önce açıklandığı gibi bir çağrı tarafından döndürülen bir değer olmalıdır. Bu tür bir NULL olmayan değer için varsayılan davranış `ptr` önceki çağrı tarafından ayrılan depolama alanını geri kazanmak için. Hangi koşullar altında bir sonraki çağrı tarafından ayrılır kısmını veya tamamını reclaimed gibi depolama belirtilmeyen [new işleci](../standard-library/new-operators.md#op_new)( **size_t**), ya da herhangi bir `calloc`( **size_t**), `malloc`( **size_t**), veya `realloc`( **void\***, **size_t**).

İkinci işlev yerleştirme tarafından çağrılır `delete[]` ifade ile eşleşen bir `new[]` biçiminde ifade `new[]`( **std::size_t**). Hiçbir şey yapmaz.

Üçüncü işlevi bir yerleştirme delete ifade ile eşleşen tarafından çağrılır bir `new[]` biçiminde ifade `new[]`( **std::size_t**, **const std::nothrow_t &**). Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir bu işlev imzası işleviyle tanımlayabilirsiniz. Değerini kabul etmek için gerekli davranıştır `ptr` yani null ya da işleç için önceki bir çağrı tarafından döndürülen `new[]`( **size_t**). Değerlendirmek için varsayılan davranıştır `delete[]`( `ptr`).

### <a name="example"></a>Örnek

Bkz: [new işleci&#91; &#93; ](../standard-library/new-operators.md#op_new_arr) kullanımını örnekleri için `operator delete[]`.

## <a name="op_new"></a>  new işleci

Yeni-ayrı ayrı nesneleri için depolama alanı ayırmak için ifadesi tarafından çağrılan işlev.

```cpp
void* operator new(std::size_t count) throw(bad_alloc);

void* operator new(std::size_t count,
    const std::nothrow_t&) throw();

void* operator new(std::size_t count,
    void* ptr) throw();
```

### <a name="parameters"></a>Parametreler

`count` Ayrılacak Depolama bayt sayısı.

`ptr` Döndürülecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılmış depolama en düşük bayt adresini gösteren bir işaretçi. Veya `ptr.`

### <a name="remarks"></a>Açıklamalar

İlk işlev ayırmak için yeni bir ifade tarafından çağrılır `count` uygun depolama bayt hizalı bu boyut herhangi bir nesne temsil etmek için. Program bir alternatif işlevi C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir ve bu nedenle değiştirebilen bu işlev imzası ile tanımlayabilirsiniz.

Gerekli istendiği gibi depolama yalnızca ayrılabilen ise NULL olmayan bir işaretçi döndürülecek davranıştır. Her tür ayırma bir işaretçi diğer ayrılmış depolama alanından depolama ayrık verir. Art arda gelen çağrıları tarafından ayrılmış depolama contiguity ve sırası belirtilmemiş. İlk depolanan değer belirtilmedi. Döndürülen işaretçi noktaları ayrılan depolama alanı başlatma (en düşük bayt adresi). Sayısı sıfır ise, döndürülen değer işlev tarafından döndürülen değer eşit karşılaştırın değil.

Döngü yürütmek için varsayılan davranıştır. Döngü içinde işlevi ilk istenen depolama alanı ayırmaya çalışır. Girişimini yapılan bir çağrı içerir olup olmadığını `malloc`( **size_t**) belirtilmedi. Deneme başarılı olursa, işlevi ayrılan depolama alanı için bir işaretçi döndürür. Aksi takdirde işlevi belirlenen çağırır [yeni işleyicisi](../standard-library/new-typedefs.md#new_handler). Çağrılan işlev durumunda döndürür, döngü tekrarlar. Döngü istenen depolama ayırma denemesi başarılı olduğunda veya çağrılan işlev döndürmez sonlandırır.

Yeni bir işleyici gerekli davranışını aşağıdaki işlemlerden birini gerçekleştirmektir:

- Daha fazla depolama alanı ayırma için kullanılabilir hale getirmek ve ardından döndürür.

- Ya da çağrısı **abort** veya **çıkmak**( `int`).

- Nesne türüne throw **bad_alloc.**

Varsayılan davranışının bir [yeni işleyicisi](../standard-library/new-typedefs.md#new_handler) nesne türüne throw için `bad_alloc`. Null işaretçinin varsayılan yeni işleyicisi belirler.

Sırasını ve art arda gelen çağrıları tarafından ayrılmış depolama contiguity `operator new`( **size_t**) depolanan ilk değerleri olarak belirtilmedi.

İkinci işlev ayırmak için bir yerleştirme yeni ifadesi tarafından çağrılır `count` uygun depolama bayt hizalı bu boyut herhangi bir nesne temsil etmek için. Program bir alternatif işlevi C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir ve bu nedenle değiştirebilen bu işlev imzası ile tanımlayabilirsiniz.

Döndürülecek varsayılan davranıştır `operator new`( `count`) Bu işlev başarılı olursa. Aksi takdirde null işaretçi döndürür.

Üçüncü işlev yerleştirme tarafından çağrılır **yeni** biçiminde ifade **yeni** ( *args*) t Burada, *args* bir tek nesne işaretçisi oluşur. Bu, bilinen bir adreste bir nesne oluşturmak için yararlı olabilir. İşlevi döndürür *ptr*.

Tarafından ayrılan depolama alanını boşaltmak için `operator new`, çağrı [delete işleci](../standard-library/new-operators.md#op_delete).

Atma hakkında bilgi için veya yeni, bkz: nonthrowing davranışını [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md).

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

Ayırma işlevi nesnelerinin bir dizisi için depolama alanı ayırmak için yeni bir ifade tarafından çağrılır.

```cpp
void* operator new[](std::size_t count) throw(std::bad_alloc);

void* operator new[](std::size_t count,
    const std::nothrow_t&) throw();

void* operator new[](std::size_t count,
    void* ptr) throw();
```

### <a name="parameters"></a>Parametreler

`count` Dizi nesnesi için ayrılacak depolama bayt sayısı.

`ptr` Döndürülecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılmış depolama en düşük bayt adresini gösteren bir işaretçi. Veya `ptr.`

### <a name="remarks"></a>Açıklamalar

İlk işlev tarafından çağrılır bir `new[]` ayırmak için ifade `count` bayt depolama uygun o boyuttaki tüm dizi nesnesini temsil eden hizalanmış ya da daha küçük. Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir bu işlev imzası işleviyle tanımlayabilirsiniz. Gerekli aynı davranıştır [new işleci](../standard-library/new-operators.md#op_new)( **size_t**). Döndürülecek varsayılan davranıştır `operator new`( `count`).

İkinci işlev yerleştirme tarafından çağrılır `new[]` ayırmak için ifade `count` uygun depolama bayt hizalı bu boyut herhangi bir dizi nesne temsil etmek için. Program C++ Standart Kitaplığı tarafından tanımlanan varsayılan sürümü değiştirir bu işlev imzası işleviyle tanımlayabilirsiniz. Döndürülecek varsayılan davranıştır **operatornew**( `count`) Bu işlev başarılı olursa. Aksi takdirde null işaretçi döndürür.

Üçüncü işlev yerleştirme tarafından çağrılır `new[]` biçiminde ifade **yeni** ( *args*) **T**[ **N**]. Burada, *args* bir tek nesne işaretçisi oluşur. İşlevi döndürür `ptr`.

Tarafından ayrılan depolama alanını boşaltmak için `operator new[]`, çağrı [delete işleci&#91;&#93;](../standard-library/new-operators.md#op_delete_arr).

Atma hakkında bilgi için veya yeni, bkz: nonthrowing davranışını [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md).

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
