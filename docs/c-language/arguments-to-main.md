---
title: "Main bağımsız değişkenleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aa4dda9a8735f0b57dd6dcefa0f16774c006da35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="arguments-to-main"></a>main Bağımsız Değişkenleri
**ANSI 2.1.2.2.1** main bağımsız değişkenleri semantiği  
  
 Microsoft C programı başlangıçta çağrılan işlev çağrılır **ana**. İçin bildirilen hiçbir prototip yoktur **ana**, ve sıfır, iki veya üç parametrelerle tanımlanabilir:  
  
```  
int main( void )  
int main( int argc, char *argv[] )  
int main( int argc, char *argv[], char *envp[] )  
```  
  
 Üçüncü satır yukarıda, where **ana** üç parametre kabul eder, ANSI C standart bir Microsoft uzantısıdır. Üçüncü parametre **envp**, ortam değişkenleri işaretçiler dizisidir. **Envp** dizi null işaretçinin tarafından sonlandırıldı. Bkz: [main işlevi ve Program yürütme](../c-language/main-function-and-program-execution.md) hakkında daha fazla bilgi için **ana** ve **envp**.  
  
 Değişkeni **argc** hiçbir zaman negatif bir değer içerir.  
  
 Dize dizisi bitip ile **argv [argc]**, boş bir işaretçi içeriyor.  
  
 Tüm öğeleri **argv** dizi dizeleri işaretçileri olan.  
  
 Komut satırı bağımsız değişkenler olmadan çağrılan bir program için bir tane değerini alacak **argc**yürütülebilir dosyanın adını yerleştirilir gibi **argv [0]**. (3.0'dan önceki MS-DOS sürümlerinde, yürütülebilir dosya adı kullanılamaz. "C" harf yerleştirilir **argv [0]**.) Tarafından için dizeleri işaret **argv [1]** aracılığıyla **argv [argc - 1]** program parametreleri temsil eder.  
  
 Parametreleri **argc** ve **argv** değiştirilebilir ve program başlatma ve program sonlandırma arasında son depolanan değerlerini korur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortamı](../c-language/environment.md)