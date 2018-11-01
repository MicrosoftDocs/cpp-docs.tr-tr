---
title: Bağlayıcı Araçları Hatası LNK1211
ms.date: 12/05/2017
f1_keywords:
- LNK1211
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
ms.openlocfilehash: 7c918cacb87460c2aad30285b750d9b170425534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456153"
---
# <a name="linker-tools-error-lnk1211"></a>Bağlayıcı Araçları Hatası LNK1211

> önceden derlenmiş tür bilgileri bulunamadı; '*filename*' bağlı değil veya üzerine

*Filename* kullanarak derlenen nesne dosyası, [/Yc](../../build/reference/yc-create-precompiled-header-file.md), bağlantı komutunda belirtilmedi veya yazıldı.

Önceden derlenmiş üst bilgiler kullanan hata ayıklama kitaplığı oluşturuyorsanız ve belirtirseniz **/Yc** ve [/z7](../../build/reference/z7-zi-zi-debug-information-format.md), Visual C++ hata ayıklama bilgilerini içeren bir önceden derlenen nesne dosyası oluşturur. Yalnızca ne zaman önceden derlenen nesne dosyası bir kitaplıkta depoladığınız bir hata oluşursa, kitaplığı bir yürütülebilir görüntü oluşturmak için kullanın ve başvurulan nesne dosyaları geçişli başvurularınız önceden derlenen nesne dosyası tanımlar işlevlerden herhangi birinin için.

Bu durumu çözmek için iki yöntem vardır:

- Belirtin [/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) derleyici seçeneği önceden derlenmiş üst bilgisinden her nesne modülü için hata ayıklama bilgileri eklenecek. Bu yöntem, genellikle bir uygulamayı bağlamak için gereken süreyi artırabilir büyük nesne modülleri oluşturur çünkü daha az tercih edilir.

- Belirtin [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) ve herhangi bir işlev tanımı içermiyor bir ön derlenmiş üstbilgi dosyası oluşturduğunuzda, herhangi bir rastgele dize adını geçirin. Bu, derleyicinin önceden derlenen nesne dosyasında bir simge oluşturmak ve önceden derlenen nesne dosyası ile ilişkili önceden derlenmiş üst bilgi dosyası kullanılan her nesne dosyasında bu sembole bir başvuru yaymak için yönlendirir.

Bir modül ile derleme yaparken **/Yc** ve **/Yl**, derleyici benzer bir simge oluşturur `__@@_PchSym_@00@...@symbol_name`burada üç nokta (...) derleyici tarafından oluşturulan bir karakter dizesini temsil eder ve depolar Nesne modülü. Bu önceden derlenmiş üstbilgiyle derleme dilediğiniz kaynak dosyaya nesne modülü ve kitaplığı hata ayıklama bilgilerini dahil etmesini bağlayıcıya neden belirtilen sembol ifade eder.
