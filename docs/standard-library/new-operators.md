---
description: 'Daha fazla bilgi edinin: &lt; Yeni &gt; İşleçler ve numaralandırmalar'
title: '&lt;Yeni &gt; İşleçler ve numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- new/std::operator delete
- new/std::operator new
ms.assetid: d1af4b56-9a95-4c65-ab01-bf43e982c7bd
ms.openlocfilehash: e5b6a675b200c80dc56778a66d63d5940561eb1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338171"
---
# <a name="ltnewgt-operators-and-enums"></a>&lt;Yeni &gt; İşleçler ve numaralandırmalar

## <a name="enum-align_val_t"></a><a name="op_align_val_t"></a> Enum align_val_t

```cpp
enum class align_val_t : size_t {};
```

## <a name="operator-delete"></a><a name="op_delete"></a> delete işleci

Nesneler için depolama alanını serbest bırakmak için bir Delete ifadesi tarafından çağrılan işlev.

```cpp
void operator delete(void* ptr) throw();
void operator delete(void *, void*) throw();
void operator delete(void* ptr, const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Değeri, silme işlemi tarafından geçersiz işlenecek olan işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk işlev, *PTR* 'nin değerini işlemek için bir Delete ifadesi tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplığı tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Gerekli davranış, null olan veya daha önceki [işleç](../standard-library/new-operators.md#op_new)(**size_t**) çağrısıyla döndürülen bir *PTR* değerini kabul etmelidir.

Bir *PTR* null değeri için varsayılan davranış hiçbir şey yapmaz. Diğer bir *PTR* değeri, daha önce açıklandığı gibi bir çağrı tarafından daha önce döndürülen bir değer olmalıdır. Bu tür null olmayan bir *PTR* değeri için varsayılan davranış, önceki çağrı tarafından ayrılan depolamayı geri kazanmalıdır. Bu, bir veya daha fazla geri kazanılan depolamanın, ( `operator new` **size_t**) veya herhangi bir `calloc` ( **size_t**), `malloc` ( **size_t**) veya `realloc` ( **`void`** <strong>\*</strong> , **size_t**) çağrısı tarafından ayrıldığı koşullarda belirtilmemiş.

İkinci işlev, formun yeni ifadesine karşılık gelen yerleştirme silme ifadesiyle çağrılır **`new`** ( **std:: size_t**). Hiçbir şey yapmaz.

Üçüncü işlev, formun yeni ifadesine karşılık gelen yerleştirme silme ifadesi tarafından çağrılır **`new`** ( **std:: size_t**, **conststd:: nothrow_t&**). Program, bu işlev imzasıyla C++ standart kitaplığı tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Gerekli davranış, `ptr` null olan veya daha önceki bir çağrı tarafından döndürülen `operator new` ( **size_t**) bir değerini kabul etmelidir. Varsayılan davranış, () öğesini değerlendirmek için kullanılır **`delete`** `ptr` .

### <a name="example"></a>Örnek

**İşleç Delete** kullanan bir örnek için bkz. [New işleci](../standard-library/new-operators.md#op_new) .

## <a name="operator-delete"></a><a name="op_delete_arr"></a> delete [] işleci

Bir nesne dizisi için depolamayı serbest bırakmak için bir Delete ifadesi tarafından çağrılan işlev.

```cpp
void operator delete[](void* ptr) throw();
void operator delete[](void *, void*) throw();
void operator delete[](void* ptr, const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Değeri, silme işlemi tarafından geçersiz işlenecek olan işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk işlev, `delete[]` *PTR* değerini işlemek için bir ifade tarafından çağırılır geçersiz. Program, C++ standart kitaplığı tarafından tanımlanan varsayılan sürümü değiştiren bu işlev imzasıyla bir işlev tanımlayabildiğinden işlev değiştirilebilir. Gerekli davranış, null olan bir *PTR* değerini kabul etmetir veya daha önceki bir [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)(**size_t**) çağrısıyla döndürülür. Bir *PTR* null değeri için varsayılan davranış hiçbir şey yapmaz. Diğer bir *PTR* değeri, daha önce açıklandığı gibi bir çağrı tarafından daha önce döndürülen bir değer olmalıdır. Bu tür bir null olmayan *PTR* değeri için varsayılan davranış, önceki çağrı tarafından ayrılan depolamayı geri kazanmalıdır. Bu, bir veya daha fazla geri kazanılan depolamanın, [Yeni operatör](../standard-library/new-operators.md#op_new)(**size_t**) veya herhangi bir `calloc` (**size_t**), `malloc` (**size_t**) veya `realloc` ( **`void`** <strong>\*</strong> , **size_t**) çağrısı tarafından ayrıldığı koşullarda belirtilmemiş.

İkinci işlev, `delete[]` formun ifadesine karşılık gelen bir yerleştirme ifadesi tarafından çağrılır `new[]` `new[]` (**std:: size_t**). Hiçbir şey yapmaz.

Üçüncü işlev, formun ifadesine karşılık gelen yerleştirme silme ifadesi tarafından çağrılır `new[]` `new[]` ( **std:: size_t**, **const std:: nothrow_t&**). Program, bu işlev imzasıyla C++ standart kitaplığı tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Gerekli davranış, null olan veya daha önceki bir işleç çağrısıyla döndürülen bir *PTR* değerini kabul etmek `new[]` (**size_t**). Varsayılan davranış, () öğesini değerlendirmek için kullanılır `delete[]` `ptr` .

### <a name="example"></a>Örnek

Kullanım örnekleri için bkz. [New operator&#91;&#93;](../standard-library/new-operators.md#op_new_arr) `operator delete[]` .

## <a name="operator-new"></a><a name="op_new"></a> New işleci

Tek tek nesneler için depolama alanı ayırmak üzere yeni bir ifade tarafından çağrılan işlev.

```cpp
void* operator new(std::size_t count) throw(bad_alloc);
void* operator new(std::size_t count, const std::nothrow_t&) throw();
void* operator new(std::size_t count, void* ptr) throw();
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Ayrılacak depolamanın bayt sayısı.

*kaydetmeye*\
Döndürülecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan depolamanın en düşük bayt adresine yönelik bir işaretçi. Veya *PTR*.

### <a name="remarks"></a>Açıklamalar

İlk işlev, `count` Bu boyuttaki herhangi bir nesneyi temsil edecek şekilde hizalı bir depolama uygun şekilde bayt ayırmak için yeni bir ifade tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplığı tarafından tanımlanan varsayılan sürümü değiştiren alternatif bir işlev tanımlayabilir, bu nedenle değiştirilebilir.

Gerekli davranış, yalnızca depolama istenen şekilde ayrılabileceği takdirde null olmayan bir işaretçi döndürmelidir. Her bir ayırma, depolama için diğer ayrılmış depolardan kopuk bir işaretçi verir. Art arda çağrılar tarafından ayrılan depolamanın sırası ve contiguity belirtilmemiş. İlk depolanan değer belirtilmemiş. Döndürülen işaretçi ayrılan depolamanın başlangıcını (en düşük bayt adresini) işaret eder. Count değeri sıfırsa döndürülen değer, işlev tarafından döndürülen diğer bir değere eşit olarak karşılaştırmaz.

Varsayılan davranış bir döngü yürütmeniz olur. Döngü içinde, işlev önce istenen depolamayı ayırmaya çalışır. Girişimin `malloc` ( **size_t**) çağrısı içerip içermediğini belirtir. Deneme başarılı olursa, işlev ayrılmış depolamaya bir işaretçi döndürür. Aksi takdirde, işlev belirlenen [Yeni işleyiciyi](../standard-library/new-typedefs.md#new_handler)çağırır. Çağrılan işlev döndürürse, döngü yinelenir. İstek, istenen depolamayı ayırma girişimi başarılı olduğunda veya çağrılan bir işlev dönzaman sonlandırıldığında sonlanır.

Yeni bir işleyicinin gerekli davranışı, aşağıdaki işlemlerden birini gerçekleştirdir:

- Daha fazla depolama alanı ayırma için kullanılabilir hale getirin ve ardından döndürün.

- Ya da ' i çağırın `abort` `exit` .

- Türünde bir nesne oluşturur `bad_alloc` .

[Yeni bir işleyicinin](../standard-library/new-typedefs.md#new_handler) varsayılan davranışı türünde bir nesne oluşturmak şeklindedir `bad_alloc` . Null işaretçi varsayılan yeni işleyiciyi belirler.

Art arda yapılan çağrılar (size_t) tarafından ayrılan depolama ve contiguity, `operator new` burada depolanan ilk değerler gibi belirtilmemiş.

İkinci işlev, `count` Bu boyuttaki herhangi bir nesneyi temsil edecek şekilde hizalı bir depolama uygun şekilde bayt ayırmak için yerleştirme yeni bir ifade tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplığı tarafından tanımlanan varsayılan sürümü değiştiren alternatif bir işlev tanımlayabilir, bu nedenle değiştirilebilir.

Varsayılan davranış, `operator new` ( `count` ) işlevi başarılı olursa döndürülür. Aksi halde, null bir işaretçi döndürür.

Üçüncü işlev, formun yerleştirme ifadesi tarafından çağrılır **`new`** `new ( args ) T` . Burada, *bağımsız değişkenler* tek bir nesne işaretçisinden oluşur. Bu, bilinen bir adreste bir nesne oluşturmak için yararlı olabilir. İşlev *PTR* döndürür.

**New işlecine** göre ayrılan depolama alanını serbest bırakmak için [işleç silme](../standard-library/new-operators.md#op_delete)çağrısı yapın.

Yeni bir oluşturma veya atma davranışı hakkında bilgi için bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md).

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

## <a name="operator-new"></a><a name="op_new_arr"></a> New işleci []

Bir nesne dizisi için depolama alanı ayırmak üzere yeni bir ifade tarafından çağrılan ayırma işlevi.

```cpp
void* operator new[](std::size_t count) throw(std::bad_alloc);
void* operator new[](std::size_t count, const std::nothrow_t&) throw();
void* operator new[](std::size_t count, void* ptr) throw();
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Dizi nesnesi için ayrılacak depolamanın bayt sayısı.

*kaydetmeye*\
Döndürülecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan depolamanın en düşük bayt adresine yönelik bir işaretçi. Veya *PTR*.

### <a name="remarks"></a>Açıklamalar

İlk işlev, `new[]` `count` Bu boyuttaki veya daha küçük bir dizi nesnesini temsil edecek şekilde hizalı bir depolama uygun şekilde bayt ayırmak için bir ifade tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplığı tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Gerekli davranış, [New işleci](../standard-library/new-operators.md#op_new)(**size_t**) ile aynıdır. Varsayılan davranış () dönmemelidir `operator new` `count` .

İkinci işlev, `new[]` `count` Bu boyuttaki herhangi bir dizi nesnesini temsil edecek şekilde hizalı depolama uygun şekilde için bayt ayırmak üzere bir yerleştirme ifadesi tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplığı tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Varsayılan davranış, **operatornew**( `count` ) işlevinin başarılı olması durumunda döndürülür. Aksi halde, null bir işaretçi döndürür.

Üçüncü işlev `new[]` , **`new`** ( *args*) **T**[ **N**] biçiminde bir yerleştirme ifadesi tarafından çağırılır. Burada, *bağımsız değişkenler* tek bir nesne işaretçisinden oluşur. İşlev döndürür `ptr` .

Tarafından ayrılan depolamayı serbest bırakmak için `operator new[]` , [işleç silme&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)çağırın.

Yeni, oluşturma veya atma davranışı hakkında bilgi için bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md).

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
