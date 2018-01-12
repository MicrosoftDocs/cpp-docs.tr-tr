---
title: "ATL Sihirbazı tarafından eklenen ATL desteğinin ayrıntıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.atl.support
dev_langs: C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17d5063db9eb76e0fc6db9eecfe183b63276b874
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>ATL Sihirbazı Tarafından Eklenen ATL Desteğinin Ayrıntıları
Olduğunda, [varolan bir MFC yürütülebilir veya DLL ATL desteği ekleme](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C++ varolan MFC projesine aşağıdaki değişiklikleri yapar (Bu örnekte, proje adlı `MFCEXE`):  
  
-   İki yeni dosyalar (.idl dosya ve sunucuyu kaydetmek için kullanılan bir .rgs dosyası) eklenir.  
  
-   Ana uygulama başlığı ve uygulama dosyaları (Mfcexe.h ve Mfcexe.cpp), yeni bir sınıf (türetilmiş **CAtlMFCModule**) eklenir. Yeni sınıf yanı sıra kodu eklenen `InitInstance` kaydı için. Kodu da eklenir `ExitInstance` sınıf nesnesi iptal etmek için işlev. Üstbilgi dosyasında dosyasında bildirme ve yeni GUID'lerini başlatma uygulaması, son olarak, iki yeni üstbilgi dosyaları (Initguid.h ve Mfcexe_i.c) içerdiği **CAtlMFCModule**-türetilmiş sınıf.  
  
-   Sunucuyu düzgün kaydetmek için yeni .rgs dosyası için bir giriş projenin kaynak dosyasına eklenir.  
  
## <a name="notes-for-dll-projects"></a>DLL projeleri için Notlar  
 MFC DLL projesinde ATL desteği eklediğinizde, bazı farklar görürsünüz. Kod eklenir **DLLRegisterServer** ve **DLLUnregisterServer** kaydetme ve kaydını DLL işlevleri. Kodu da eklenir [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) ve [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC projesinde ATL desteği](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
