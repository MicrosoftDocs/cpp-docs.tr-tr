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
ms.openlocfilehash: c1f83f794cc40fa7f4d290fa4a147fe9f7e074be
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508367"
---
# <a name="initinstance-member-function"></a>InitInstance Üye İşlevi

Windows işletim sistemi, aynı uygulamanın birden fazla kopyasını veya "örneğini" çalıştırmanızı sağlar. `WinMain`uygulamanın her yeni örneği başlatıldığında [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) 'ı çağırır.

MFC Uygulama `InitInstance` Sihirbazı tarafından oluşturulan standart uygulama aşağıdaki görevleri gerçekleştirir:

- Merkezi eylemi olarak, belge, görünüm ve çerçeve pencereleri oluşturan belge şablonlarını oluşturur. Bu işlemin açıklaması için bkz. [belge şablonu oluşturma](../mfc/document-template-creation.md).

- En son kullanılan dosyaların adları da dahil olmak üzere bir. ini dosyasından veya Windows kayıt defterinden standart dosya seçeneklerini yükler.

- Bir veya daha fazla belge şablonunu kaydeder.

- MDI uygulaması için bir ana çerçeve penceresi oluşturur.

- Komut satırında belirtilen bir belgeyi açmak veya yeni, boş bir belge açmak için komut satırını işler.

Kendi başlatma kodunuzu ekleyebilir veya sihirbaz tarafından yazılan kodu değiştirebilirsiniz.

> [!NOTE]
>  MFC uygulamalarının tek iş parçacıklı grup (STA) olarak başlatılması gerekir. `InitInstance` Geçersiz kılmada [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) öğesini çağırırsanız, COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED yerine) belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
