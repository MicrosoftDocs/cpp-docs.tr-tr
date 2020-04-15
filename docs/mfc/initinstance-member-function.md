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
ms.openlocfilehash: 2cf5b266348e299fe761ba40bd2cfb849f02b9ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377191"
---
# <a name="initinstance-member-function"></a>InitInstance Üye İşlevi

Windows işletim sistemi, aynı uygulamanın birden fazla kopyasını veya "örneğini" çalıştırmanızı sağlar. `WinMain`uygulamanın yeni bir örneği her başlatında [InitInstance'ı](../mfc/reference/cwinapp-class.md#initinstance) çağırır.

MFC `InitInstance` Uygulama Sihirbazı tarafından oluşturulan standart uygulama aşağıdaki görevleri gerçekleştirir:

- Merkezi eylemi olarak, sırayla belgeler, görünümler ve çerçeve pencereleri oluşturmak belge şablonları oluşturur. Bu işlemin açıklaması için [Bkz. Belge Şablonu Oluşturma.](../mfc/document-template-creation.md)

- En son kullanılan dosyaların adları da dahil olmak üzere bir .ini dosyasından veya Windows kayıt defterinden standart dosya seçenekleri yükler.

- Bir veya daha fazla belge şablonu kaydeder.

- Bir MDI uygulaması için bir ana çerçeve penceresi oluşturur.

- Komut satırında belirtilen bir belgeyi açmak veya yeni, boş bir belgeyi açmak için komut satırını işler.

Kendi başlatma kodunuzu ekleyebilir veya sihirbaz tarafından yazılan kodu değiştirebilirsiniz.

> [!NOTE]
> MFC uygulamaları tek dişli daire (STA) olarak başharfe getirilmelidir. Geçersiz kılmada `InitInstance` [CoInitializeEx'i](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) ararsanız, COINIT_APARTMENTTHREADED belirtin (COINIT_MULTITHREADED yerine).

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
