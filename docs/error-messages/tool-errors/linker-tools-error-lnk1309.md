---
title: "Bağlayıcı araçları hatası LNK1309 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1309
dev_langs: C++
helpviewer_keywords: LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: febaeeeabdf045ee7d223b7514d63202ded1e99c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1309"></a>Bağlayıcı Araçları Hatası LNK1309
type1 modülü; algılandı anahtar /CLRIMAGETYPE:type2 ile geçersiz  
  
 Bir CLR görüntü türü ile istendi **/CLRIMAGETYPE** ancak bir veya daha fazla modül bu türüyle uyumlu olduğundan bağlayıcı türü görüntüsünü oluşturamadı.  
  
 Belirtirseniz, örneğin, LNK1309 göreceğiniz **/CLRIMAGETYPE:safe** ve ile yerleşik bir modül geçirdiğiniz **/CLR: pure**.  
  
 Ptrustu [d] .lib kullanarak kısmen güvenilen bir CLR saf uygulaması oluşturma çalışırsanız, ayrıca LNK1309 görürsünüz. Kısmen güvenilir uygulama oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: CRT kitaplık DLL bağımlılık kaldırma tarafından bir kısmen güvenilir uygulama oluşturma](../../dotnet/create-a-partially-trusted-application.md).  
  
 Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [/CLRIMAGETYPE (belirtin, CLR Resim türünde)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).