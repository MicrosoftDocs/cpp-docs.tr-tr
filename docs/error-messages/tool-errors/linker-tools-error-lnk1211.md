---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1211'
title: Bağlayıcı Araçları Hatası LNK1211
ms.date: 12/05/2017
f1_keywords:
- LNK1211
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
ms.openlocfilehash: d3201055643f5874ccc319f04fb6eb2d976bf67f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341626"
---
# <a name="linker-tools-error-lnk1211"></a>Bağlayıcı Araçları Hatası LNK1211

> önceden derlenmiş tür bilgileri bulunamadı; '*filename*' bağlı değil veya üzerine yazıldı

[/Rivc](../../build/reference/yc-create-precompiled-header-file.md)kullanılarak derlenen *filename* nesne dosyası, bağlantı komutunda belirtilmemiş veya üzerine yazıldı.

Önceden derlenmiş üstbilgileri kullanan bir hata ayıklama kitaplığı oluşturuyorsanız ve **/Yıc** ve [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)belirtirseniz, Visual C++ hata ayıklama bilgilerini içeren önceden derlenmiş bir nesne dosyası oluşturur. Hata yalnızca önceden derlenmiş nesne dosyasını bir kitaplıkta depoladığınız zaman oluşur, bir yürütülebilir görüntü oluşturmak için kitaplığı kullanın ve başvurulan nesne dosyalarının önceden derlenmiş nesne dosyasının tanımladığı işlevlerden herhangi birine geçişli başvuruları yoktur.

Bu durumu çözmek için iki yöntem vardır:

- Ön derlenmiş üstbilgideki hata ayıklama bilgilerini her bir nesne modülüne eklemek için [/yd](../../build/reference/yd-place-debug-information-in-object-file.md) derleyici seçeneğini belirtin. Bu yöntem, genellikle uygulamayı bağlamak için gereken süreyi arttırabileceğiniz büyük nesne modülleri oluşturduğundan daha az tercih edilir.

- Herhangi bir işlev tanımı içermeyen ön derlenmiş üstbilgi dosyası oluşturduğunuzda, [/Rivl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) belirtin ve herhangi bir rastgele dizenin adını geçirin. Bu, derleyicinin önceden derlenmiş nesne dosyasında bir sembol oluşturmasını ve önceden derlenmiş nesne dosyasıyla ilişkili olan ön derlenmiş üst bilgi dosyasını kullanan her nesne dosyasında bu simgeye bir başvuru yaymasına olanak sağlar.

**/İ** ve **/rivl** ile bir modül derlerken, derleyici öğesine benzer bir sembol oluşturur `__@@_PchSym_@00@...@symbol_name` ; burada üç nokta (...) derleyici tarafından oluşturulan bir karakter dizesini temsil eder ve bunu nesne modülünde depolar. Bu ön derlenmiş üstbilgi ile derleyebileceğiniz herhangi bir kaynak dosya, bağlayıcının nesne modülünü ve hata ayıklama bilgilerini kitaplıktan içermesini sağlayan, belirtilen simgeye başvurur.
