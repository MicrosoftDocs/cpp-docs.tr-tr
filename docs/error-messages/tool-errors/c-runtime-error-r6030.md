---
title: "C çalışma zamanı hatası R6030 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6030
dev_langs: C++
helpviewer_keywords: R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 328f4dac5ec772ec7229c7a4b4a21ed408d3ad73
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6030"></a>C çalışma zamanı hatası R6030
CRT başlatılmadı  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, dahili bir sorun olduğundan uygulama kapatıldı. Bu sorunu en sık belirli güvenlik yazılımı programları veya nadiren, programın bir hatadan kaynaklanır.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Güvenlik yazılımının bu sorunu Azaltıcı yönelik özel yönergeler olabilir. Ayrıntılar için güvenlik yazılım satıcısının Web sitesini denetleyin. Alternatif olarak, güvenlik yazılımının güncelleştirilmiş sürümlerini denetleyin veya farklı güvenlik yazılımı deneyin.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 C çalışma zamanı (CRT) kullanıyorsanız, ancak CRT başlatma kodunu yürütülmedi bu hata oluşur. Bağlayıcı geçerseniz bu hatayı almak olası [/Entry](../../build/reference/entry-entry-point-symbol.md) başlangıç adresi, genellikle varsayılan geçersiz kılmak için kullanılan **mainCRTStartup**, **wmainCRTStartup** için bir Konsol EXE **WinMainCRTStartup** veya **wWinMainCRTStartup** Windows EXE için veya **_DllMainCRTStartup** bir DLL için. Yukarıdaki işlevleri birini başlangıçta adlandırılır sürece C çalışma zamanı başlatılmayacak. C Çalışma Zamanı Kitaplığı'na bağlamak ve normal kullandığınızda bu başlangıç İşlevler normalde varsayılan olarak adlandırılır **ana**, **wmain**, **WinMain**, veya  **DllMain** giriş noktaları.  
  
 Başka bir program bazı DLL Kitaplığı çağrıları yakalamak için kod ekleme teknikleri kullandığında bu hatayı almaya mümkündür. Bu teknik bazı zorlayıcı güvenlik programlarını kullanın. Visual C++ Visual Studio 2015 tarihinden önceki sürümlerinde, sorunu gidermek için bir statik olarak bağlantılı CRT kitaplık kullanmak da mümkündür, ancak bu güvenlik ve uygulama güncelleştirmelerini nedenleriyle önerilmez. Bu sorunu düzeltme son kullanıcı eylemi gerektirebilir.