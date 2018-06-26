---
title: InitInstance üye işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- InitInstance
dev_langs:
- C++
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9379fef6a1d676d6a3bc757ee51d5d27acd5f6f
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930182"
---
# <a name="initinstance-member-function"></a>InitInstance Üye İşlevi
Windows işletim sisteminin birden fazla kopya veya "aynı uygulamanın" örnek çalıştırmanıza olanak sağlar. `WinMain` çağrıları [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) her zaman uygulamanın yeni bir örneğini başlatır.  
  
 Standart `InitInstance` MFC Uygulama Sihirbazı tarafından oluşturulan uygulama aşağıdaki görevleri gerçekleştirir:  
  
-   Kendi merkezi eylem olarak sırayla belgeler, görünümler ve çerçeve pencereleri oluşturma belge şablonu oluşturur. Bu işlem açıklaması için bkz: [belge şablonu oluşturma](../mfc/document-template-creation.md).  
  
-   Standart dosya seçenekleri bir .ini dosyası veya en son kullanılan dosya adlarını dahil olmak üzere Windows kayıt defterinden yükler.  
  
-   Bir veya daha fazla belge şablonları kaydeder.  
  
-   MDI uygulama için bir ana çerçeve penceresi oluşturur.  
  
-   Komut satırı komut satırında belirtilen bir belgeyi açmaya veya yeni, boş bir belgeyi açmak için işler.  
  
 Sihirbaz tarafından yazılan kodu değiştirin ya da kendi başlatma kodunu ekleyin.  
  
> [!NOTE]
>  MFC uygulamaları tek iş parçacıklı (STA) başlatılması gerekir. Çağırırsanız [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) içinde `InitInstance` geçersiz kılma, COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED yerine) belirtin. Daha fazla bilgi için bkz: MFC uygulaması olarak bir birden çok iş parçacıklı grup (828643) uygulama başlattığınızda yanıt vermiyor [ http://support.microsoft.com/default.aspxscid=kb; en-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
