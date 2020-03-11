---
title: Yeni&gt; işleçleri ve numaralandırmalar &lt;
ms.date: 11/04/2016
f1_keywords:
- new/std::operator delete
- new/std::operator new
ms.assetid: d1af4b56-9a95-4c65-ab01-bf43e982c7bd
ms.openlocfilehash: a3fd5b825fe1eaf3a07d9d001f03b9d0c64ffa31
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78854958"
---
# <a name="ltnewgt-operators-and-enums"></a>Yeni&gt; işleçleri ve numaralandırmalar &lt;

## <a name="op_align_val_t"></a>Enum align_val_t

```cpp
enum class align_val_t : size_t {};
```

## <a name="op_delete"></a>delete işleci

Nesneler için depolama alanını serbest bırakmak için bir Delete ifadesi tarafından çağrılan işlev.

```cpp
void operator delete(void* ptr) throw();
void operator delete(void *, void*) throw();
void operator delete(void* ptr, const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parametreler

*ptr*\
Değeri, silme işlemi tarafından geçersiz işlenecek olan işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk işlev, *PTR* 'nin değerini işlemek için bir Delete ifadesi tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplık tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Gerekli davranış, null olan veya daha önceki [işleç](../standard-library/new-operators.md#op_new)(**size_t**) çağrısıyla döndürülen bir *PTR* değerini kabul etmelidir.

Bir *PTR* null değeri için varsayılan davranış hiçbir şey yapmaz. Diğer bir *PTR* değeri, daha önce açıklandığı gibi bir çağrı tarafından daha önce döndürülen bir değer olmalıdır. Bu tür null olmayan bir *PTR* değeri için varsayılan davranış, önceki çağrı tarafından ayrılan depolamayı geri kazanmalıdır. `operator new`(**size_t**) veya `calloc`( **size_t**), `malloc`( **size_t**) veya `realloc`( **void** <strong>\*</strong>, **size_t**) ' e yapılan bir çağrı tarafından bir veya daha fazla geri kazanılan depolamanın hangi koşullarda ayrıldığı belirtilmemiş.

İkinci işlev, **Yeni**( **std:: size_t**) biçiminde yeni bir ifadeye karşılık gelen bir yerleştirme silme ifadesi tarafından çağrılır. Hiçbir şey yapmaz.

Üçüncü işlev **Yeni**( **std:: size_t**, **conststd:: nothrow_t &** ) biçiminde yeni bir ifadeye karşılık gelen bir yerleşim silme ifadesi tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplık tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Gerekli davranış, null olan veya daha önceki bir `operator new`( **size_t**) çağrısıyla döndürülen `ptr` değerini kabul etmelidir. Varsayılan davranış **silme**(`ptr`) öğesini değerlendirmektir.

### <a name="example"></a>Örnek

**İşleç Delete**kullanan bir örnek için bkz. [New işleci](../standard-library/new-operators.md#op_new) .

## <a name="op_delete_arr"></a>delete [] işleci

Bir nesne dizisi için depolamayı serbest bırakmak için bir Delete ifadesi tarafından çağrılan işlev.

```cpp
void operator delete[](void* ptr) throw();
void operator delete[](void *, void*) throw();
void operator delete[](void* ptr, const std::nothrow_t&) throw();
```

### <a name="parameters"></a>Parametreler

*ptr*\
Değeri, silme işlemi tarafından geçersiz işlenecek olan işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk işlev `delete[]` bir ifade tarafından çağrılır, bu da *PTR* değerini işlemek için geçersiz. Program, C++ standart kitaplık tarafından tanımlanan varsayılan sürümü değiştiren bu işlev imzasıyla bir işlev tanımlayabildiğinden işlev değiştirilebilir. Gerekli davranış, null olan veya daha önceki [&#91;işleç](../standard-library/new-operators.md#op_new_arr)(**size_t**) çağrısıyla döndürülen bir *PTR* değerini kabul etmelidir. Bir *PTR* null değeri için varsayılan davranış hiçbir şey yapmaz. Diğer bir *PTR* değeri, daha önce açıklandığı gibi bir çağrı tarafından daha önce döndürülen bir değer olmalıdır. Bu tür bir null olmayan *PTR* değeri için varsayılan davranış, önceki çağrı tarafından ayrılan depolamayı geri kazanmalıdır. Bu, bir veya daha fazla geri kazanılan depolamanın, [Yeni operatör](../standard-library/new-operators.md#op_new)(**size_t**) veya herhangi bir `calloc`(**size_t**), `malloc`(**size_t**) veya `realloc`( **void** <strong>\*</strong>, **size_t**) çağrısı tarafından ayrıldığı koşullarda belirtilmemiş.

İkinci işlev, form `new[]`bir `new[]` ifadesine karşılık gelen bir yerleştirme `delete[]` ifadesi tarafından çağrılır (**std:: size_t**). Hiçbir şey yapmaz.

Üçüncü işlev `new[]`form `new[]` ifadesine karşılık gelen yerleştirme silme ifadesi tarafından çağrılır ( **std:: size_t**, **const std:: nothrow_t &** ). Program, bu işlev imzasıyla C++ standart kitaplık tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Gerekli davranış, null veya daha önceki bir işleç `new[]`(**size_t**) çağrısıyla döndürülen bir *PTR* değerini kabul etmelidir. Varsayılan davranış `delete[]`(`ptr`) değerlendirmelidir.

### <a name="example"></a>Örnek

`operator delete[]`kullanımı örnekleri için bkz. [New&#91; işleci](../standard-library/new-operators.md#op_new_arr) .

## <a name="op_new"></a>New işleci

Tek tek nesneler için depolama alanı ayırmak üzere yeni bir ifade tarafından çağrılan işlev.

```cpp
void* operator new(std::size_t count) throw(bad_alloc);
void* operator new(std::size_t count, const std::nothrow_t&) throw();
void* operator new(std::size_t count, void* ptr) throw();
```

### <a name="parameters"></a>Parametreler

*sayı*\
Ayrılacak depolamanın bayt sayısı.

*ptr*\
Döndürülecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan depolamanın en düşük bayt adresine yönelik bir işaretçi. Veya *PTR*.

### <a name="remarks"></a>Açıklamalar

İlk işlev, bu boyuttaki herhangi bir nesneyi temsil edecek şekilde hizalı `count` Byte for Storage uygun şekilde ayırması için yeni bir ifade tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplık tarafından tanımlanan varsayılan sürümü değiştiren alternatif bir işlev tanımlayabilir ve bu nedenle değiştirilebilir.

Gerekli davranış, yalnızca depolama istenen şekilde ayrılabileceği takdirde null olmayan bir işaretçi döndürmelidir. Her bir ayırma, depolama için diğer ayrılmış depolardan kopuk bir işaretçi verir. Art arda çağrılar tarafından ayrılan depolamanın sırası ve contiguity belirtilmemiş. İlk depolanan değer belirtilmemiş. Döndürülen işaretçi ayrılan depolamanın başlangıcını (en düşük bayt adresini) işaret eder. Count değeri sıfırsa döndürülen değer, işlev tarafından döndürülen diğer bir değere eşit olarak karşılaştırmaz.

Varsayılan davranış bir döngü yürütmeniz olur. Döngü içinde, işlev önce istenen depolamayı ayırmaya çalışır. Girişimin `malloc`( **size_t**) çağrısı içerip içermediğini belirtir. Deneme başarılı olursa, işlev ayrılmış depolamaya bir işaretçi döndürür. Aksi takdirde, işlev belirlenen [Yeni işleyiciyi](../standard-library/new-typedefs.md#new_handler)çağırır. Çağrılan işlev döndürürse, döngü yinelenir. İstek, istenen depolamayı ayırma girişimi başarılı olduğunda veya çağrılan bir işlev dönzaman sonlandırıldığında sonlanır.

Yeni bir işleyicinin gerekli davranışı, aşağıdaki işlemlerden birini gerçekleştirdir:

- Daha fazla depolama alanı ayırma için kullanılabilir hale getirin ve ardından döndürün.

- **Abort** veya **Exit**(`int`) çağrısı yapın.

- Bad_alloc türünde bir nesne oluşturun **.**

[Yeni bir işleyicinin](../standard-library/new-typedefs.md#new_handler) varsayılan davranışı `bad_alloc`türünde bir nesne oluşturmak. Null işaretçi varsayılan yeni işleyiciyi belirler.

`operator new`(**size_t**) için art arda çağrılar tarafından ayrılan depolamanın sırası ve contiguity değeri, burada depolanan ilk değerler gibi belirtilmemiş.

İkinci işlev, bu boyuttaki herhangi bir nesneyi temsil edecek şekilde hizalı `count` Byte for Storage uygun şekilde ayırmak için yerleştirme yeni bir ifade tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplık tarafından tanımlanan varsayılan sürümü değiştiren alternatif bir işlev tanımlayabilir ve bu nedenle değiştirilebilir.

Varsayılan davranış, bu işlev başarılı olursa `operator new`(`count`) döndürmelidir. Aksi halde, null bir işaretçi döndürür.

Üçüncü işlev **Yeni** ( *args*) T biçiminde yerleştirme **Yeni** bir ifade tarafından çağırılır. Burada, *bağımsız değişkenler* tek bir nesne işaretçisinden oluşur. Bu, bilinen bir adreste bir nesne oluşturmak için yararlı olabilir. İşlev *PTR*döndürür.

**New işlecine**göre ayrılan depolama alanını serbest bırakmak için [işleç silme](../standard-library/new-operators.md#op_delete)çağrısı yapın.

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

## <a name="op_new_arr"></a>New işleci []

Bir nesne dizisi için depolama alanı ayırmak üzere yeni bir ifade tarafından çağrılan ayırma işlevi.

```cpp
void* operator new[](std::size_t count) throw(std::bad_alloc);
void* operator new[](std::size_t count, const std::nothrow_t&) throw();
void* operator new[](std::size_t count, void* ptr) throw();
```

### <a name="parameters"></a>Parametreler

*sayı*\
Dizi nesnesi için ayrılacak depolamanın bayt sayısı.

*ptr*\
Döndürülecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan depolamanın en düşük bayt adresine yönelik bir işaretçi. Veya *PTR*.

### <a name="remarks"></a>Açıklamalar

İlk işlev, bu boyuttaki veya daha küçük bir dizi nesnesini temsil etmek üzere uygun şekilde bir depolama alanına hizalı bir `new[]` `count` ifadesi tarafından çağrılır. Program, bu işlev imzasıyla C++ standart kitaplık tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Gerekli davranış, [New işleci](../standard-library/new-operators.md#op_new)(**size_t**) ile aynıdır. Varsayılan davranış `operator new`(`count`) döndürmelidir.

İkinci işlev, bu boyuttaki herhangi bir dizi nesnesini temsil edecek şekilde hizalı `count` Byte for Storage `new[]` ayırmak için bir yerleştirme ifadesi tarafından çağırılır. Program, bu işlev imzasıyla C++ standart kitaplık tarafından tanımlanan varsayılan sürümü değiştiren bir işlev tanımlayabilir. Varsayılan davranış, bu işlev başarılı olursa **operatornew**(`count`) döndürmelidir. Aksi halde, null bir işaretçi döndürür.

Üçüncü işlev, **Yeni** ( *args*) **t**[ **N**] biçiminde bir yerleştirme `new[]` ifadesi tarafından çağrılır. Burada, *bağımsız değişkenler* tek bir nesne işaretçisinden oluşur. İşlev `ptr`döndürür.

`operator new[]`tarafından ayrılan depolamayı serbest bırakmak için [işleç silme&#91;](../standard-library/new-operators.md#op_delete_arr)çağrısı yapın.

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
