---
title: "Başvuru türleri için C++ yığın anlamları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8f4bf38fa6512b0dc86edad43c893d2dd09a97a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-stack-semantics-for-reference-types"></a>Referans Türleri için C++ Yığın Anlamları
Visual C++ 2005 önce başvuru türünde bir örneği yalnızca kullanarak oluşturulabilir `new` Atık nesne oluşturulan işleci toplanan yığın. Bununla birlikte, artık yığında yerel türünün bir örneği oluşturmak için kullanacağınız aynı sözdizimini kullanarak bir başvuru türünde bir örnek oluşturabilirsiniz. Bu nedenle, kullanmak gerekmez [yeni başvuru, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) başvuru türünde bir nesne oluşturmak için. Ve nesne kapsam dışına çıktığında derleyici nesnenin yıkıcı çağırır.  
  
## <a name="remarks"></a>Açıklamalar  
 Yığın anlamları kullanarak bir başvuru türünde bir örnek oluşturduğunuzda, derleyici dahili olarak örneği atık toplanan yığında oluşturun (kullanarak `gcnew`).  
  
 Bir işlev imzası veya return türü değeri olarak başvuru türünde bir örnek içerdiğinde, işlevi meta veriler (ile modreq) özel işlem gerektiren olarak işaretlenir. Bu özel işleme şu anda değil yalnızca Visual C++ istemciler tarafından; sağlanan Diğer diller şu anda süren işlevleri veya yığın anlamları ile oluşturulan başvuru türleri kullandığı verileri desteklemez.  
  
 Kullanmak için bir neden `gcnew` (dinamik ayırma) yerine yığın anlamları türü hiçbir yıkıcı olup olmadığını olacaktır. Ayrıca, başvuru türleri işlevi imzaları yığın anlamları ile oluşturulan kullanarak Visual C++ dışındaki dilleri tarafından tüketilmesi işlevlerinizi istiyorsanız mümkün olmayacaktır.  
  
 Derleyici bir başvuru türü için bir kopya Oluşturucu oluşturmaz. Bu nedenle, bir değer tarafından başvuru türü imzada kullanan bir işlev tanımlarsanız, başvuru türü için bir kopya Oluşturucu tanımlamanız gerekir. Kopya Oluşturucu bir başvuru türü için aşağıdaki biçimde bir imzaya sahip: `R(R%){}`.  
  
 Derleyici bir başvuru türü için varsayılan atama işleci oluşturmaz. Atama işleci yığın anlamları kullanan bir nesne oluşturma ve yığın anlamları kullanarak oluşturduğunuz varolan bir nesneyle başlatma izin verir. Bir başvuru türü için bir atama işleci bir imza aşağıdaki biçime sahiptir: `void operator=( R% ){}`.  
  
 Tür yıkıcı kritik kaynakları serbest bırakır ve başvuru türleri için yığın anlamları kullanırsanız, açıkça yıkıcı çağırma gerekmez (veya çağrı `delete`). Başvuru türlerindeki Yıkıcılar hakkında daha fazla bilgi için bkz: [yok ediciler ve sonlandırıcılar nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Derleyicinin ürettiği atama işleci normal standart C++ kurallar aşağıdaki eklemelerle izler:  
  
-   Bir başvuru türü için bir tanıtıcı türü olan üyeleri herhangi bir statik olmayan veri kopyalanan (bir işaretçi türü olan bir statik olmayan veri üyesi gibi kabul edilir) basit.  
  
-   Değer türü basit türü olan herhangi bir statik olmayan veri üyesi kopyalanır.  
  
-   Bir başvuru türünde bir örnek türü olan herhangi bir statik olmayan veri üyesi başvuru tür kopya Oluşturucu için bir çağrı çağıracaktır.  
  
 Ayrıca, derleyicinin sağlar bir `%` , temel alınan tanıtıcı türü için yığın anlamları kullanılarak oluşturulan bir başvuru türünde bir örnek dönüştürmek için birli işleç.  
  
 Aşağıdaki başvuru türleri yığın anlamları ile kullanmak için kullanılabilir değil:  
  
-   [temsilci (C++ Bileşen Uzantıları)](../windows/delegate-cpp-component-extensions.md)  
  
-   [Diziler](../windows/arrays-cpp-component-extensions.md)  
  
-   <xref:System.String>  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneği, yığın anlamları başvuru türleriyle örneklerini bildirmek gösterilmiştir nasıl atama işleci ve kopya Oluşturucu çalışır ve nasıl izleme başvurusu yığın anlamları kullanılarak oluşturulan başvuru türü ile başlatılamıyor.  
  
### <a name="code"></a>Kod  
  
```  
// stack_semantics_for_reference_types.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
   R(){}  
  
   // assignment operator  
   void operator=(R% r) {  
      i = r.i;  
   }  
  
   // copy constructor  
   R(R% r) : i(r.i) {}  
};  
  
void Test(R r) {}   // requires copy constructor  
  
int main() {  
   R r1;  
   r1.i = 98;  
  
   R r2(r1);   // requires copy constructor  
   System::Console::WriteLine(r1.i);  
   System::Console::WriteLine(r2.i);  
  
   // use % unary operator to convert instance using stack semantics  
   // to its underlying handle  
   R ^ r3 = %r1;  
   System::Console::WriteLine(r3->i);  
  
   Test(r1);  
  
   R r4;  
   R r5;  
   r5.i = 13;  
   r4 = r5;   // requires a user-defined assignment operator  
   System::Console::WriteLine(r4.i);  
  
   // initialize tracking reference  
   R % r6 = r4;  
   System::Console::WriteLine(r6.i);  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
98  
98  
98  
13  
13  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)