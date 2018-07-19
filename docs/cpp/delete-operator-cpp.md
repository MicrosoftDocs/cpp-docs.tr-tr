---
title: delete işleci (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- delete_cpp
dev_langs:
- C++
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89ad061dc2be090abbcfbc147f1ea5fbddb8ae6a
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948030"
---
# <a name="delete-operator-c"></a>delete İşleci (C++)
Bellek bloğunu kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Atama ifadesini* bağımsız değişkeni olmalıdır daha önce oluşturulmuş bir nesne için ayrılan bellek bloğuna işaretçi [new işleci](../cpp/new-operator-cpp.md). **Sil** işleci bir sonuç türü olan **void** ve bu nedenle bir değer döndürmez. Örneğin:  
  
```cpp 
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 Kullanarak **Sil** ile ayrılmamış bir nesnenin işaretçisinde **yeni** beklenmeyen sonuçlar verir. Ancak, kullanabileceğiniz **Sil** değeri 0 olan bir işaretçi üzerinde. Bu olmayacağı anlamına gelir, **yeni** başarısız sonucu silme, hata durumunda 0 döndürür **yeni** işlemdir zararsız. Bkz: [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md) daha fazla bilgi için.  
  
 **Yeni** ve **Sil** işleçleri diziler de dahil olmak üzere yerleşik türler için de kullanılabilir. `pointer` bir diziye başvuruyorsa, `pointer` öncesinde boş köşeli ayraçlar yerleştirin.  
  
```cpp 
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 Kullanarak **Sil** işlecini bir nesne üzerinde kullanmak onun belleğini kaldırır. Nesne silindikten sonra bir işaretçinin başvurusunu kaldıran bir program öngörülemeyen sonuçlara veya çökmeye neden olabilir.  
  
 Zaman **Sil** olan bir C++ sınıfı nesne için bellek ayırması için kullanılan (nesnenin bir yok Edicisi varsa) nesnenin belleği kaldırılmadan önce nesnenin yok Edicisi çağrılır.  
  
 İşlenenin **Sil** işleci değiştirilebilir bir l-değeri ise, nesne silindikten sonra değeri tanımsızdır.  
  
## <a name="using-delete"></a>delete Kullanma  
 İçin söz dizimi iki çeşidi vardır [delete işleci](../cpp/delete-operator-cpp.md): tek nesneleri ve diğer nesne dizileri için. Aşağıdaki kod parçası bu farkı göstermektedir:  
  
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
  
 Aşağıdaki iki durum tanımsız sonuçlar: dizi biçimi Sil (delete []) bir nesne üzerinde ve bir dizi üzerinde silme formülü biçimini kullanarak.  
  
## <a name="example"></a>Örnek  
 Kullanım örnekleri **Sil**, bkz: [new işleci](../cpp/new-operator-cpp.md).  
  
## <a name="how-delete-works"></a>Delete nasıl çalışır  
 Delete işlecinin işlevi çağıran **delete işleci**.  
  
 Sınıf türündeki nesneler için ([sınıfı](../cpp/class-cpp.md), [yapı](../cpp/struct-cpp.md), veya [birleşim](../cpp/unions.md)), genel delete işleci çağrılır. Sınıf türü nesneler için ifadeyi silmenin birli kapsam çözümleme işleci (:) ile başlıyorsa ayırmayı kaldırma işlevinin adını genel kapsamda çözülür. Aksi takdirde, delete işleci (işaretçi null değilse) belleğini önce nesnenin yok Edicisi çağırır. Delete işleci, sınıf başına temelinde tanımlanabilir; belirli bir sınıfın tür tanımı yok ise, global işleci silme çağrılır. Sanal bir yıkıcı statik türü olan bir sınıf nesnesi ayırması için ifadeyi silmenin kullandıysanız, ayırmayı kaldırma işlevi nesne dinamik türden sanal yıkıcı çözümlenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [new ve delete İşleçleri](../cpp/new-and-delete-operators.md)   
 
