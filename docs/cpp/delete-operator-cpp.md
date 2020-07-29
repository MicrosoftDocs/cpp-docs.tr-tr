---
title: delete İşleci (C++)
ms.date: 08/12/2019
f1_keywords:
- delete_cpp
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
ms.openlocfilehash: 19f92e2aa62adf1ede4c0e6ab1187fd9e4106e68
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221698"
---
# <a name="delete-operator-c"></a>delete İşleci (C++)

Bellek bloğunu kaldırır.

## <a name="syntax"></a>Sözdizimi

> [ `::` ] `delete` *Cast ifadesi*\
> [ `::` ] `delete []` *Cast ifadesi*

## <a name="remarks"></a>Açıklamalar

*Cast ifadesi* bağımsız değişkeni, [New işleciyle](../cpp/new-operator-cpp.md)oluşturulmuş bir nesne için daha önce ayrılmış bir bellek bloğunun işaretçisi olmalıdır. **`delete`** İşlecinin türü bir sonucu vardır **`void`** ve bu nedenle bir değer döndürmez. Örnek:

```cpp
CDialog* MyDialog = new CDialog;
// use MyDialog
delete MyDialog;
```

**`delete`** Atanmamış bir nesne işaretçisi üzerinde kullanılması **`new`** öngörülemeyen sonuçlara neden olur. Ancak, **`delete`** değeri 0 olan bir işaretçi üzerinde kullanabilirsiniz. Bu sağlama, **`new`** hata durumunda 0 ' ı döndürdüğünde başarısız bir işlemin sonucunu silmenin **`new`** zararsız olduğu anlamına gelir. Daha fazla bilgi için bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md).

**`new`** Ve **`delete`** işleçleri diziler dahil yerleşik türler için de kullanılabilir. `pointer`Bir diziye başvuruyorsa, önüne boş köşeli ayraçlar ( `[]` ) yerleştirin `pointer` :

```cpp
int* set = new int[100];
//use set[]
delete [] set;
```

**`delete`** İşleci bir nesne üzerinde kullanmak, belleğini ayırır. Nesne silindikten sonra bir işaretçinin başvurusunu kaldıran bir program öngörülemeyen sonuçlara veya çökmeye neden olabilir.

**`delete`** Bir C++ sınıf nesnesi için belleği serbest bırakmak için kullanıldığında, nesnenin yıkıcısı, nesnenin belleği serbest bırakılmadan önce çağrılır (nesne bir yıkıcı içeriyorsa).

**`delete`** İşlecin işleneni değiştirilebilir bir l-değeri ise, nesne silindikten sonra değeri tanımsız olur.

[/SDL (ek güvenlik denetimlerini etkinleştir)](/cpp/build/reference/sdl-enable-additional-security-checks) derleyici seçeneği belirtilmişse, işleç işleneni, **`delete`** nesne silindikten sonra geçersiz bir değere ayarlanır.

## <a name="using-delete"></a>delete Kullanma

[Delete işleci](../cpp/delete-operator-cpp.md)için bir tane olmak üzere iki sözdizimi vardır: tek nesneler ve diğeri de nesne dizileri için. Aşağıdaki kod parçası bunların nasıl farklı olduğunu gösterir:

```cpp
// expre_Using_delete.cpp
struct UDType
{
};

int main()
{
   // Allocate a user-defined object, UDObject, and an object
   //  of type double on the free store using the
   //  new operator.
   UDType *UDObject = new UDType;
   double *dObject = new double;
   // Delete the two objects.
   delete UDObject;
   delete dObject;
   // Allocate an array of user-defined objects on the
   // free store using the new operator.
   UDType (*UDArr)[7] = new UDType[5][7];
   // Use the array syntax to delete the array of objects.
   delete [] UDArr;
}
```

Aşağıdaki iki durum tanımsız sonuçlar üretir: bir nesnede Delete () dizi formunu kullanarak `delete []` ve dizi üzerinde Delete () dizi olmayan formunu kullanarak.

## <a name="example"></a>Örnek

Using örnekleri için **`delete`** bkz. [New Operator](../cpp/new-operator-cpp.md).

## <a name="how-delete-works"></a>Silme nasıl kullanılır?

Delete işleci, **Delete işlev işlecini**çağırır.

Sınıf türü olmayan nesneler için ([Class](../cpp/class-cpp.md), [struct](../cpp/struct-cpp.md)veya [Union](../cpp/unions.md)), genel delete işleci çağrılır. Sınıf türündeki nesneler için, DELETE ifadesi birli kapsam çözümleme işleci () ile başlıyorsa, ayırmayı kaldırma işlevinin adı genel kapsamda çözümlenir `::` . Aksi takdirde, delete işleci, bellek ayırmayı yapmadan önce bir nesne için yıkıcıyı çağırır (işaretçi null değilse). Delete işleci sınıf başına ayrı olarak tanımlanabilir; belirli bir sınıf için böyle bir tanım yoksa, genel işleç silme işlemi çağrılır. Statik türünün sanal yok edicisi olan bir sınıf nesnesini serbest bırakmak için Delete ifadesi kullanılırsa, ayırmayı kaldırma işlevi nesnenin dinamik türünün sanal yıkıcısı aracılığıyla çözümlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)\
[Lerimi](../cpp/keywords-cpp.md)\
[New ve DELETE Işleçleri](../cpp/new-and-delete-operators.md)
