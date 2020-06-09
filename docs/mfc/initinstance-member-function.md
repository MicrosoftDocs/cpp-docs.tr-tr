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
ms.openlocfilehash: 0a458f19f956bb1092cc76acd587bc467f25325e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625577"
---
# <a name="initinstance-member-function"></a>InitInstance Üye İşlevi

Windows işletim sistemi, aynı uygulamanın birden fazla kopyasını veya "örneğini" çalıştırmanızı sağlar. `WinMain`uygulamanın her yeni örneği başlatıldığında [InitInstance](reference/cwinapp-class.md#initinstance) 'ı çağırır.

`InitInstance`MFC Uygulama Sihirbazı tarafından oluşturulan standart uygulama aşağıdaki görevleri gerçekleştirir:

- Merkezi eylemi olarak, belge, görünüm ve çerçeve pencereleri oluşturan belge şablonlarını oluşturur. Bu işlemin açıklaması için bkz. [belge şablonu oluşturma](document-template-creation.md).

- En son kullanılan dosyaların adları da dahil olmak üzere bir. ini dosyasından veya Windows kayıt defterinden standart dosya seçeneklerini yükler.

- Bir veya daha fazla belge şablonunu kaydeder.

- MDI uygulaması için bir ana çerçeve penceresi oluşturur.

- Komut satırında belirtilen bir belgeyi açmak veya yeni, boş bir belge açmak için komut satırını işler.

Kendi başlatma kodunuzu ekleyebilir veya sihirbaz tarafından yazılan kodu değiştirebilirsiniz.

> [!NOTE]
> MFC uygulamalarının tek iş parçacıklı grup (STA) olarak başlatılması gerekir. Geçersiz kılmada [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) öğesini çağırırsanız `InitInstance` , COINIT_APARTMENTTHREADED belirtin (COINIT_MULTITHREADED yerine).

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](cwinapp-the-application-class.md)
