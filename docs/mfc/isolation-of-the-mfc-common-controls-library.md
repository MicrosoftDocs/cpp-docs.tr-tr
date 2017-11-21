---
title: "MFC ortak yalıtım denetimleri kitaplığı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC, Common Controls library
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: effc8b927aadc821e189837ab3506f05cb426e93
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isolation-of-the-mfc-common-controls-library"></a>MFC Ortak Denetimler Kitaplığını Yalıtma
Ortak Denetimler kitaplığı şimdi farklı modülleri (örneğin, kullanıcı DLL'ler) izin vererek MFC içinde için yalıtılmış olduğundan kendi bildirimleri sürümü belirterek ortak denetimler kitaplığı farklı sürümlerini kullanın.  
  
 Bir MFC uygulaması (veya kullanıcı kodu tarafından MFC denir) ortak denetimler kitaplığı API'leri sarmalayıcı işlevleri aracılığıyla adlı çağrılar `Afx` *FunctionName*, burada *FunctionName* bir ortak adı API denetler. Bu sarmalayıcı işlevleri afxcomctl32.h ve afxcomctl32.inl tanımlanır.  
  
 Kullanabileceğiniz [afx_comctl32_ıf_exısts](reference/run-time-object-model-services.md#afx_comctl32_if_exists) ve [afx_comctl32_ıf_exısts2](reference/run-time-object-model-services.md#afx_comctl32_if_exists2) ortak denetimler kitaplığı çağırmak yerine belirli bir API uygulayan olup olmadığını belirlemek için makroları (tanımlıysa afxcomctl32.h) [GetProcAddress](../build/getprocaddress.md).  
  
 Ortak Denetimler kitaplığı API çağrıları bir sarmalayıcı sınıfı aracılığıyla teknik olarak, yaptığınız `CComCtlWrapper` (afxcomctl32.h içinde tanımlanmış). `CComCtlWrapper`Ayrıca yükleme ve comctl32.dll eklentiyi sorumludur. MFC modül durumu örneği için bir işaretçi içeriyor `CComCtlWrapper`. Sarmalayıcı sınıfı kullanarak erişebilirsiniz `afxComCtlWrapper` makrosu.  
  
 Çağırmanın Not doğrudan ortak denetimleri API (MFC sarmalayıcı işlevleri kullanarak değil) MFC Uygulama veya kullanıcı DLL kendi bildiriminde istenen ortak denetimler kitaplığı bağlı olduğundan, bir MFC'den uygulama veya kullanıcıya DLL çoğu durumda, çalışır). Ancak, MFC kodu kullanıcı DLL'leri farklı ortak denetimler kitaplığı sürümleriyle öğesinden çağrılması çünkü sarmalayıcıları kullanmak MFC kodu vardır.

