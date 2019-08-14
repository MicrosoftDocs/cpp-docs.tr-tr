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
ms.openlocfilehash: d6e1be0b06beed8cf68a1ec90571281b592af21d
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980462"
---
# <a name="delete-operator-c"></a>delete İşleci (C++)

Bellek bloğunu kaldırır.

## <a name="syntax"></a>Sözdizimi

> [`::`] `delete` *Cast ifadesi* [`::`] Cast`delete []` *ifadesi*

## <a name="remarks"></a>Açıklamalar

*Cast ifadesi* bağımsız değişkeni, [New işleciyle](../cpp/new-operator-cpp.md)oluşturulmuş bir nesne için daha önce ayrılmış bir bellek bloğunun işaretçisi olmalıdır. **Delete** işlecinin **void** türünde bir sonucu vardır ve bu nedenle bir değer döndürmez. Örneğin:

```cpp
CDialog* MyDialog = new CDialog;
// use MyDialog
delete MyDialog;
```

**Yeni** ile ayrılmamış bir nesnenin işaretçisi üzerinde **Delete** kullanılması öngörülemeyen sonuçlara neden olur. Ancak, 0 değeriyle bir işaretçi üzerinde **Delete** kullanabilirsiniz. Bu sağlama, **Yeni** hata durumunda 0 döndürdüğünde, başarısız olan **Yeni** bir işlemin sonucunun silinmesinin zararsız olduğu anlamına gelir. Daha fazla bilgi için bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md).

**New** ve **Delete** işleçleri diziler dahil yerleşik türler için de kullanılabilir. `pointer` bir diziye başvuruyorsa, `pointer` öncesinde boş köşeli ayraçlar yerleştirin.

```cpp
int* set = new int[100];
//use set[]
delete [] set;
```

Bir nesne üzerinde **Delete** işlecinin kullanılması belleği ayırır. Nesne silindikten sonra bir işaretçinin başvurusunu kaldıran bir program öngörülemeyen sonuçlara veya çökmeye neden olabilir.

Bir C++ sınıf nesnesi için belleği serbest bırakmak için silme kullanıldığında, nesnenin yıkıcısı, nesne bellekten serbest bırakılmadan önce çağrılır (nesne bir yıkıcı içeriyorsa).

**Delete** işlecinin işleneni değiştirilebilir bir l-değeri ise, nesne silindikten sonra değeri tanımsız olur.

[/SDL (ek güvenlik denetimlerini etkinleştir)](/cpp/build/reference/sdl-enable-additional-security-checks) derleyici seçeneği belirtilmişse, **Delete** işlecinin işleneni, nesne silindikten sonra geçersiz bir değere ayarlanır.

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

Aşağıdaki iki durum tanımsız sonuçlar üretir: bir nesnede Delete () dizi formunu kullanarak`delete []`ve dizi üzerinde Delete () dizi olmayan formunu kullanarak.

## <a name="example"></a>Örnek

**Delete**kullanma örnekleri için, bkz. [New işleci](../cpp/new-operator-cpp.md).

## <a name="how-delete-works"></a>Silme nasıl kullanılır?

Delete işleci, **Delete işlev işlecini**çağırır.

Sınıf türü olmayan nesneler için ([Class](../cpp/class-cpp.md), [struct](../cpp/struct-cpp.md)veya [Union](../cpp/unions.md)), genel delete işleci çağrılır. Sınıf türündeki nesneler için, DELETE ifadesi birli kapsam çözümleme işleci (::) ile başlıyorsa, ayırmayı kaldırma işlevinin adı genel kapsamda çözümlenir. Aksi takdirde, delete işleci, bellek ayırmayı yapmadan önce bir nesne için yıkıcıyı çağırır (işaretçi null değilse). Delete işleci sınıf başına ayrı olarak tanımlanabilir; belirli bir sınıf için böyle bir tanım yoksa, genel işleç silme işlemi çağrılır. Statik türünün sanal yok edicisi olan bir sınıf nesnesini serbest bırakmak için Delete ifadesi kullanılırsa, ayırmayı kaldırma işlevi nesnenin dinamik türünün sanal yıkıcısı aracılığıyla çözümlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Birli İşleçli İfadeler](../cpp/expressions-with-unary-operators.md)<br/>
[anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[new ve delete İşleçleri](../cpp/new-and-delete-operators.md)