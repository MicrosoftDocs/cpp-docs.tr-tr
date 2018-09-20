---
title: ATL desteğinin ayrıntıları ATL Sihirbazı tarafından eklenen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.atl.support
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efa96037139e61e16b752b45617bb8a3c54be993
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442155"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>ATL Sihirbazı Tarafından Eklenen ATL Desteğinin Ayrıntıları

Olduğunda, [varolan bir MFC yürütülebilir dosyası veya DLL ATL desteği Ekle](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C++, varolan bir MFC projesine aşağıdaki değişiklikleri yapar (Bu örnekte, bir proje denir `MFCEXE`):

- İki yeni dosyası (.idl dosyasının ve sunucuyu kaydetmek için kullanılan bir .rgs dosyası) eklenir.

- Ana uygulama üst bilgi ve uygulama dosyaları (Mfcexe.h ve Mfcexe.cpp), yeni bir sınıf (türetilen `CAtlMFCModule`) eklenir. Yeni bir sınıf yanı sıra kodun ekleneceği `InitInstance` kaydı. Kodu da eklenir `ExitInstance` sınıf nesnesi iptal etmek için işlevi. Üstbilgi dosyasında bildirme ve yeni GUID'leri başlatma uygulama dosyasında, son olarak, iki yeni üst bilgi dosyaları (Initguid.h ve Mfcexe_i.c) içerdiği `CAtlMFCModule`-türetilmiş sınıf.

- Düzgün bir şekilde sunucuyu kaydetmek için yeni .rgs dosyası için bir giriş projenin kaynak dosyasına eklenir.

## <a name="notes-for-dll-projects"></a>DLL projeleri için Notlar

MFC DLL projesi için ATL desteği eklediğinizde, bazı farklılıklar görürsünüz. Kod eklenir `DLLRegisterServer` ve `DLLUnregisterServer` kaydetme ve kaydını DLL için işlevleri. Kodu da eklenir [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) ve [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).

## <a name="see-also"></a>Ayrıca Bkz.

[Bir MFC projesinde ATL desteği](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Bir sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
