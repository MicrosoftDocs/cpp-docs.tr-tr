---
title: "delete işleci (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: delete_cpp
dev_langs: C++
helpviewer_keywords:
- delete keyword [C++], syntax
- delete keyword [C++], deallocating objects
- delete keyword [C++]
ms.assetid: de39c900-3f57-489c-9598-dcb73c4b3930
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36da346329341221d43af2ec96aa17be4f819bf8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="delete-operator-c"></a>delete İşleci (C++)
Bellek bloğunu kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[::] delete cast-expression  
[::] delete [ ] cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Cast ifadesi* bağımsız değişkeni ile oluşturulan bir nesne için önceden ayrılmış bellek bloğu için bir işaretçi olmalıdır [yeni işleç](../cpp/new-operator-cpp.md). **Silmek** işleci bir sonuç türü olan `void` ve bu nedenle bir değer döndürmüyor. Örneğin:  
  
```  
CDialog* MyDialog = new CDialog;  
// use MyDialog  
delete MyDialog;  
```  
  
 Kullanarak **silmek** ile ayrılmamış bir nesne için bir işaretçi üzerinde **yeni** beklenmedik sonuçlar verir. Ancak, kullanabilirsiniz **silmek** değeri 0 olan bir işaretçi üzerinde. Bu sağlama anlamına zaman **yeni** başarısız sonucu silme hatası durumunda 0 döndürür **yeni** işlemdir zararsız. Bkz: [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md) daha fazla bilgi için.  
  
 **Yeni** ve **silmek** işleçleri diziler dahil olmak üzere yerleşik türleri için de kullanılabilir. `pointer` bir diziye başvuruyorsa, `pointer` öncesinde boş köşeli ayraçlar yerleştirin.  
  
```  
int* set = new int[100];  
//use set[]  
delete [] set;  
```  
  
 Kullanarak **silmek** nesnenin işleç kendi bellek kaldırır. Nesne silindikten sonra bir işaretçinin başvurusunu kaldıran bir program öngörülemeyen sonuçlara veya çökmeye neden olabilir.  
  
 Zaman **silmek** olan nesnenin bellek (nesne bir yıkıcı varsa) serbest önce C++ sınıf nesnesi için bellek ayırması için kullanılan, nesnenin yıkıcı adı verilir.  
  
 Varsa işlenenin **silmek** işleci değiştirilebilir l-değeri, nesnenin silindikten sonra değerler tanımsızdır.  
  
## <a name="using-delete"></a>delete Kullanma  
 İçin iki söz dizimi çeşitlemesi vardır [delete işleci](../cpp/delete-operator-cpp.md): tek nesneleri ve nesnelerin diziler için diğer için bir tane. Aşağıdaki kod parçası, nasıl bu farklılık gösterir:  
  
```  
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
  
 Aşağıdaki iki durumlarda tanımsız sonuçlar: dizi formun Delete (delete []) bir nesne üzerinde kullanma ve bir dizi formülü formun DELETE kullanma.  
  
## <a name="example"></a>Örnek  
 Kullanım örnekleri için **silmek**, bkz: [yeni işleç](../cpp/new-operator-cpp.md).  
  
## <a name="how-delete-works"></a>Delete nasıl çalışır  
 Delete işleci işlevi çağırır **delete işleci**.  
  
 Sınıf türündeki nesneler için ([sınıfı](../cpp/class-cpp.md), [yapısı](../cpp/struct-cpp.md), veya [UNION](../cpp/unions.md)), genel delete işleci çağrılır. Delete ifade birli kapsam çözümü işleci (:) ile başlıyorsa sınıfı türündeki nesneler için genel kapsamda ayırmayı kaldırma işlevin adını çözümlenir. Aksi takdirde, delete işleci (işaretçisi null değilse) bellek ayırmayı kaldırma önce bir nesne için yıkıcı çağırır. Delete işleci bir sınıf başına temelinde tanımlanabilir; belirli bir sınıf için tür tanımı yok ise, delete genel işleci çağrılır. Delete ifade sanal yıkıcı, statik türü olan bir sınıf nesnesi ayırması için kullanılırsa, ayırmayı kaldırma işlevi dinamik Nesne türünü sanal yıkıcı çözülür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [new ve delete İşleçleri](../cpp/new-and-delete-operators.md)   
 
