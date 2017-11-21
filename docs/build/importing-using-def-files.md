---
title: "DEF dosyalarını kullanarak içeri aktarma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81148525b70f3c5ff351feb9561699f3b9b5e932
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="importing-using-def-files"></a>DEF Dosyalarını Kullanarak İçeri Aktarma
Kullanmayı seçerseniz **__declspec(dllimport)** .def dosyası ile birlikte, hatalı kodlamanın bir soruna neden olasılığını azaltmak için veri SABİTİ yerine kullanılacak .def dosyası değiştirmeniz gerekir:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 Aşağıdaki tabloda nedenini gösterir.  
  
|Anahtar sözcüğü|İçeri aktarma kitaplığı'nda yayar|Dışarı aktarma|  
|-------------|---------------------------------|-------------|  
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 Kullanarak **__declspec(dllimport)** ve sabit listeleri her ikisi de `imp` sürümü ve .lib DLL ve adı açıkça bağlama izin vermek için oluşturulan kitaplığı içeri aktarın. Kullanarak **__declspec(dllimport)** ve veri listeler yalnızca `imp` adının sürümü.  
  
 Sabit kullanırsanız, aşağıdaki kod yapılarından birini kullanılabilir erişimi `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 veya  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 Ancak, veri .def dosyanızda kullanırsanız, yalnızca aşağıdaki tanımıyla derlenmiş kod değişkenine erişebileceği `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 SABİTİ kullanarak olduğundan daha riskli yöneltme ek düzeyini kullanmayı unutursanız, büyük olasılıkla alma adresi tablonun işaretçi değişkenine erişebilir — değişkenin kendisine değil. İçeri aktarma adres tablosu derleyici ve bağlayıcı tarafından salt okunur yapılmıştır çünkü bu tür sorunlar genelde bir erişim ihlali olarak bildirilebilir.  
  
 Bu durumda hesaba .def dosyası SABİTİNDE görürse geçerli Visual C++ bağlayıcı bir uyarı verir. SABİTİ kullanmak için yalnızca gerçek neden, burada üstbilgi dosyası değil listesinde bazı nesne dosyası derleyememenizdir **__declspec(dllimport)** prototipinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir uygulamaya aktarma](../build/importing-into-an-application.md)
