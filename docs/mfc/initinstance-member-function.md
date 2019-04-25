---
title: InitInstance Üye İşlevi
ms.date: 11/04/2016
f1_keywords:
- InitInstance
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
ms.openlocfilehash: c96d009cf19981a475209233ee397af1cdcb352d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219526"
---
# <a name="initinstance-member-function"></a>InitInstance Üye İşlevi

Windows işletim sisteminin birden fazla kopya veya "aynı uygulamanın" örneği çalıştırmanıza olanak sağlar. `WinMain` çağrıları [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) her zaman uygulamanın yeni bir örneğini başlatır.

Standart `InitInstance` MFC Uygulama Sihirbazı tarafından oluşturulan uygulama, aşağıdaki görevleri gerçekleştirir:

- Merkez eylem, buna karşılık, belgeler, görünümler ve çerçeve pencereleri oluşturma belge şablonları oluşturur. Bu işlem bir açıklaması için bkz: [belge şablonu oluşturma](../mfc/document-template-creation.md).

- Standart dosya seçenekleri programı bir .ini dosyası veya en son kullanılan dosya adlarını dahil olmak üzere Windows kayıt defterinde yükler.

- Bir veya daha fazla belge şablonları kaydeder.

- Bir MDI uygulaması için bir ana çerçeve penceresi oluşturur.

- Komut satırı komut satırında belirtilen belgeyi açın veya yeni, boş bir belge açmak için işler.

Sihirbaz tarafından yazılan kodu değiştirin ya da kendi başlatma kodunu ekleyin.

> [!NOTE]
>  MFC uygulamaları tek iş parçacıklı grup (STA) başlatılması gerekir. Eğer [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) içinde `InitInstance` geçersiz kılmak, COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED yerine) belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)
