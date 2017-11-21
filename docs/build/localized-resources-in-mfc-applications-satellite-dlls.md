---
title: "Yerelleştirilmiş MFC uygulamalarında kaynaklar: Uydu DLL'leri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multiple language support [C++]
- localization [C++], MFC resources
- localized resources [C++]
- MFC DLLs [C++], localizing
- DLLs [C++], localizing MFC
- resources [MFC], localizing
- resource-only DLLs [C++]
- resource-only DLLs [C++], MFC applications
- satellite DLLs [C++]
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f601c32a1fe2accec2663246a56830fda5ed930
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>MFC Uygulamalarında Yerelleştirilmiş Kaynaklar: Uydu DLL'leri
MFC sürüm 7.0 ve üzeri, Uydu DLL'leri, birden çok dil için yerelleştirilmiş uygulamaları oluşturmaya yardımcı olan bir özellik için gelişmiş destek sağlar. DLL uydu bir [yalnızca kaynak DLL](../build/creating-a-resource-only-dll.md) belirli bir dil için yerelleştirilmiş bir uygulamanın kaynaklar içeriyor. Uygulama çalışmaya başladığında, MFC yerelleştirilmiş kaynak ortamınız için en uygun otomatik olarak yükler. Örneğin, İngilizce dil kaynaklarla iki Uydu DLL'leri, biri, kaynaklarınızı ve diğer Almanca çevirisini içeren Fransızca çeviri içeren bir uygulama olabilir. Uygulamayı bir İngilizce dil sistemde çalıştırdığınızda İngilizce kaynaklarını kullanır. Fransızca sistemde, Fransızca kaynakları kullanır; Almanca sistemde, Almanca kaynakları kullanır.  
  
 MFC DLL uydu yükleme girişimleri bir MFC uygulamasında yerelleştirilmiş kaynaklar desteklemek için belirli bir dil için kaynakları içeren yerelleştirilmiş. Uydu DLL'leri adlı *ApplicationNameXXX*.dll, burada *ApplicationName* .exe veya .dll MFC, kullanarak adıdır ve *XXX* dil için üç harfli kod Kaynakları (örneğin, 'ENU' veya 'DEU').  
  
 MFC kaynak DLL'si her biri bulduğunda durdurma sırayla aşağıdaki diller için yüklemeyi dener:  
  
1.  (Windows 2000 veya sonraki bir sürümü) GetUserDefaultUILanguage() Win32 API'den döndürülen geçerli kullanıcının varsayılan kullanıcı Arabirimi dili.  
  
2.  (Windows 2000 veya sonraki bir sürümü) Belirli bir alt dili olmadan geçerli kullanıcının varsayılan kullanıcı Arabirimi dilinde (yani, ÇÖZÜCÜ [Kanada İngilizce] trk [ABD olur İngilizce]).  
  
3.  Sistemin varsayılan kullanıcı Arabirimi dili. Windows 2000 veya sonraki sürümlerde, bu GetSystemDefaultUILanguage() API'SİNDEN döndürülür. Diğer platformlarda OS dili budur.  
  
4.  Sistemin varsayılan kullanıcı Arabirimi dili, belirli bir alt dili olmadan.  
  
5.  3 harfli kod loc sahte bir dille  
  
 MFC herhangi bir Uydu DLL'leri bulamazsa, hangi kaynak uygulamada bulunan kullanır.  
  
 Örnek olarak, bir uygulama LangExample.exe MFC kullanır ve Windows 2000'de birden çok kullanıcı arabirimi sistem çalışan olduğunu varsayalım; Sistem kullanıcı Arabirimi dili trk [ABD olduğunu İngilizce] ve geçerli kullanıcının kullanıcı Arabirimi dili FRC [Kanada Fransızca] olarak ayarlayın. MFC aşağıdaki DLL'leri aşağıdaki sırayla arar:  
  
1.  LangExampleFRC.dll (kullanıcının kullanıcı Arabirimi dili).  
  
2.  LangExampleFRA.dll (Bu örnekte Fransızca (Fransa) alt dili olmadan kullanıcının kullanıcı Arabirimi dili.  
  
3.  LangExampleENU.dll (sistem UI Dili).  
  
4.  LangExampleLOC.dll.  
  
 Bu DLL'ler hiçbiri bulunamazsa, MFC LangExample.exe'deki kaynakları kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'leri](../build/dlls-in-visual-cpp.md)   
 [TN057: MFC bileşenlerini yerelleştirme](../mfc/tn057-localization-of-mfc-components.md)