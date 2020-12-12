---
description: 'Daha fazla bilgi edinin: InitInstance üye Işlevi'
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
ms.openlocfilehash: b55c5dbd665b45c74e5990b7d40a63fcd9098a9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220623"
---
# <a name="initinstance-member-function"></a>InitInstance Üye İşlevi

Windows işletim sistemi, aynı uygulamanın birden fazla kopyasını veya "örneğini" çalıştırmanızı sağlar. `WinMain` uygulamanın her yeni örneği başlatıldığında [InitInstance](reference/cwinapp-class.md#initinstance) 'ı çağırır.

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

[CWinApp: uygulama sınıfı](cwinapp-the-application-class.md)
