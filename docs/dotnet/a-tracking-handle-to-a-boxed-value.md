---
title: "Paketlenmiş değere izleme işleyicisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: boxed value types, tracking handle to
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a986dcea2eec183ae09eb9af275082922257ef76
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>Paketlenmiş Değere İzleme İşleyicisi
Değer türüne başvuru izleme işleyicisi kullanım için Visual C++ C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Kutulama CLR birleştirilmiş tür sistemi yaný ' dir. Değer türleri başvuru türleri örtülü çalışırken, durumlarını doğrudan içerir: yönetilen yığında ayrılan adlandırılmamış nesne için bir tanıtıcı adlandırılmış varlıktır. Herhangi bir değer atanması için yazın veya başlatma bir `Object`, örneğin, değer türü - bu iş, kutulama görüntünün nerede ortaya - CLR yığınına yerleştirilmesini ilk ilişkili bellek ayırma sonra değer türünün durumu kopyalanarak gerektirir ve bu anonim değer/başvuru karmasının adresini döndürüyor. Bu nedenle, bir C# ' ta yazdığında  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 kod kolaylık tarafından belirgin hale daha çok daha geçmeden yoktur. C# tasarımını yalnızca hangi işlemlerin başlık altında gerçekleşmekte olan, aynı zamanda, kendisini kutulama soyutlama karmaşıklığını. Yönetilen Uzantılar c++, diğer yandan, bu verimliliği yanlış bir hissi sunulmasını, açık bir yönerge gerektirerek kullanıcının karşılaştıkları koyar ilgilenen:  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 Visual c++'ta örtük kutulama şöyledir:  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 `__box` Anahtar sözcüğü Yönetilen Uzantılar, mevcut olan bir içinde çok önemli bir hizmet hizmet C# ve Visual Basic gibi dilinden tasarım: bir sözlük ve izleme işlemek doğrudan yönetilen yığında paketlenmiş örneği yönlendirmek için sağlar. Örneğin, aşağıdaki küçük programı göz önünde bulundurun:  
  
```  
int main() {  
   double result = 3.14159;  
   __box double * br = __box( result );  
  
   result = 2.7;   
   *br = 2.17;     
   Object * o = br;  
  
   Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
   Console::WriteLine( S"result :: {0}", __box(result) ) ;  
   Console::WriteLine( S"result :: {0}", br );  
}  
```  
  
 Üç çağrısı için üretilen arka plandaki kod `WriteLine` paketlenmiş değere değerini erişme çeşitli maliyetlerini yazın (Yves bu farklılıkları işaret eden için değerine sayesinde), burada gösterilen satırlar her ile ilgili ek yükü Göster Göster çağırma.  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
call       void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", __box(result) ) ;  
Ldstr    " result :: {0}"  
ldloc.0  
box    [mscorlib]System.Double // box overhead  
call    void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", br );  
ldstr    "result :: {0}"  
ldloc.0  
call     void [mscorlib]System.Console::WriteLine(string, object)  
```  
  
 Paketlenmiş değer türü doğrudan geçirme `Console::WriteLine` kutulamayı ve çağırma gereğini ortadan kaldırır `ToString()`. (Kuşkusuz başlatmak için önceki kutulama yoktur `br`, gerçekten put sürece herhangi bir şey elde yok `br` çalışmak için.  
  
 Yeni sözdiziminde paketlenmiş değer türleri için destek gücünü korurken önemli ölçüde daha zarif ve tür sistemi tümleşiktir. Örneğin, önceki küçük programın çevrilmesi şöyledir:  
  
```  
int main()  
{  
   double result = 3.14159;  
   double^ br = result;  
   result = 2.7;  
   *br = 2.17;  
   Object^ o = br;  
   Console::WriteLine( "result :: {0}", result.ToString() );  
   Console::WriteLine( "result :: {0}", result );  
   Console::WriteLine( "result :: {0}", br );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Değer türleri ve davranışları (C + +/ CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Nasıl yapılır: açık şekilde istek paketleme](../dotnet/how-to-explicitly-request-boxing.md)