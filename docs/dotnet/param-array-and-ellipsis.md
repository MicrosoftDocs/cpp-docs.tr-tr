---
title: Param dizisi ve üç nokta | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function overloading, argument matching
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 20d13f327abe3e864007c4941af2ce9fd03ea05d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="param-array-and-ellipsis"></a>Param Dizisi ve Üç Nokta
Aşırı yüklenmiş işlev çağrılarını çözmek için param dizisi önceliği Visual C++ için C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Yönetilen Uzantılar ve yeni sözdizimini C# ve Visual Basic destek param dizisi için açık desteği yoktur. Bunun yerine, bir sıradan bir dizi bir özniteliği olan şekilde işaretler:  
  
```  
void Trace1( String* format, [ParamArray]Object* args[] );  
void Trace2( String* format, Object* args[] );  
```  
  
 Bu her ikisi de aynı konum sırada `ParamArray` özniteliği etiketler bu C# veya diğer CLR diller için her çağrıldığında öğeleriyle değişken sayıda çıkarmadan bir dizi olarak. Üç nokta hangi bir örnek bildirir ayarlamak Aşırı yüklenen bir işlevin çözünürlük Yönetilen Uzantılar ve yeni sözdizimini arasında programlarda davranışında değişiklik olduğunu ve ikinci bir bildirir bir `ParamArray` tarafından sağlanan aşağıdaki örnekteki gibi özniteliği Artur Laksberg.  
  
```  
int fx(...); // 1  
int fx( [ParamArray] Int32[] ); // 2  
```  
  
 Yönetilen Uzantılar'üç nokta önceliği öznitelik resmi bir dil durumuyla olmadığından makul özniteliğinin verildi. Ancak, yeni sözdiziminde param dizisi artık doğrudan dil içinde desteklenir ve daha güçlü yazıldığından üç nokta üzerinde öncelik verilir. Bu nedenle, Yönetilen Uzantılar ' çağrısı  
  
```  
fx( 1, 2 );  
```  
  
 çözümler `fx(...)` yeni sözdiziminde karşın, bu çözümler `ParamArray` örneği. Program davranışı çağrılması üç nokta örneği ile ilgili olan bağlıdır kapalı fırsat üzerinde `ParamArray`, imza veya çağrı değiştirmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Dil Değişiklikleri (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)