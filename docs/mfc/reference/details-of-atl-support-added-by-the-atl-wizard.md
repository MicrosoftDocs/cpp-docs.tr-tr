---
description: 'Daha fazla bilgi edinin: ATL Sihirbazı tarafından eklenen ATL desteğinin ayrıntıları'
title: ATL Sihirbazı Tarafından Eklenen ATL Desteğinin Ayrıntıları
ms.date: 08/20/2019
f1_keywords:
- vc.codewiz.atl.support
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
ms.openlocfilehash: 2ae574ac2c4d56e1522fa8c794c18b6f9b6635ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220142"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>ATL Sihirbazı Tarafından Eklenen ATL Desteğinin Ayrıntıları

::: moniker range=">=msvc-160"

[Mevcut BIR MFC yürütülebilir dosyasına veya dll 'SINE atl desteği eklediğinizde](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual Studio varsayılan olarak *Framework. h* adlı bir başlık dosyası ekler ve bu, `#include` `#define` projenizde ATL kullanımını etkinleştirmek için önişlemci yönergelerini içerir. Visual Studio 'nun önceki sürümlerinde yapıldığı gibi ek dosya veya sınıflar eklenmez.

::: moniker-end

::: moniker range="<=msvc-150"

[Mevcut BIR MFC yürütülebilir dosyasına veya dll 'SINE atl desteği eklediğinizde](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual Studio var olan MFC projesinde aşağıdaki değişiklikleri yapar (Bu örnekte, proje çağrılır `MFCEXE` ):

- İki yeni dosya (sunucusunu kaydetmek için kullanılan bir. IDL dosyası ve bir. rgs dosyası) eklenir.

- Ana uygulama üst bilgisinde ve uygulama dosyalarında (Mfcexe. h ve Mfcexe. cpp), yeni bir sınıf (öğesinden türetilmiş `CAtlMFCModule` ) eklenir. Yeni sınıfa ek olarak, kod `InitInstance` kayıt için öğesine eklenir. Kod, `ExitInstance` sınıf nesnesini iptal etmek için işlevine de eklenir. Son olarak, üst bilgi dosyasında, iki yeni üstbilgi dosyası (Initguid. h ve Mfcexe_i. c) uygulama dosyasında bulunur, bu,-türetilmiş sınıf için yeni GUID 'Ler bildirip başlatılıyor `CAtlMFCModule` .

- Sunucuyu düzgün bir şekilde kaydetmek için, projenin kaynak dosyasına yeni. rgs dosyası girişi eklenir.

::: moniker-end

## <a name="notes-for-dll-projects"></a>DLL projeleri için notlar

Bir MFC DLL projesine ATL desteği eklediğinizde bazı farklılıklar görürsünüz. Kodu öğesine `DLLRegisterServer` ve `DLLUnregisterServer` DLL kaydı ve kaydını silme işlevlerine eklenir. Kod ayrıca [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) ve [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject)öğesine de eklenir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC projesinde ATL desteği](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye Işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Sanal Işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Ileti Işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigate-code-cpp.md)
