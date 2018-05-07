---
title: Bağlayıcı araçları hatası LNK1211 | Microsoft Docs
ms.date: 12/05/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1211
dev_langs:
- C++
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57948556ae7b94b9a1788b7cb4453646b5b504f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1211"></a>Bağlayıcı Araçları Hatası LNK1211

> önceden derlenmiş türü bilgileri; bulunamadı '*filename*' bağlantılı veya üzerine değil

*Filename* kullanarak derlenen nesne dosyası [/Yc](../../build/reference/yc-create-precompiled-header-file.md), bağlantı komutunda belirtilmedi veya yazıldı.

Önceden derlenmiş üst bilgileri kullanan bir hata ayıklama kitaplığı oluşturuyorsanız ve belirtirseniz **/Yc** ve [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), Visual C++ hata ayıklama bilgilerini içeren bir önceden derlenmiş nesnesi dosyası oluşturur. Yalnızca zaman, önceden derlenmiş nesne dosyası kitaplıkta depolamasına oluşur, yürütülebilir bir görüntü oluşturmak için kitaplığı kullanmasına ve başvurulan nesne dosyaları hiçbir geçişli önceden derlenmiş nesne dosyası tanımlar işlevleri hiçbirini başvuran.

Bu durumu çözmek için iki yöntem vardır:

- Belirtin [/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) hata ayıklama bilgileri önceden derlenmiş başlığından her nesne modül eklemek için derleyici seçeneği. Genellikle uygulama bağlamak için gereken süreyi artırabilir büyük nesne modülleri oluşturduğundan bu yöntem daha az tercih edilir.

- Belirtin [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) ve herhangi bir işlev tanımları içermeyen bir önceden derlenmiş üst bilgi dosyası oluşturduğunuzda herhangi bir rastgele dize adını geçirin. Önceden derlenmiş nesne dosyasında bir simge oluşturmak ve bu simgeyi önceden derlenmiş nesne dosyasıyla ilişkili önceden derlenmiş üst bilgi dosyası kullanılan her bir nesne dosyadaki başvuru yayma için derleyici yönlendirir.

Derleme zaman sahip bir modül **/Yc** ve **/Yl**, derleyici benzer bir simge oluşturur `__@@_PchSym_@00@...@symbol_name`, burada üç nokta (...) derleyicinin ürettiği karakter dizesini temsil eder ve depolar Nesne Modül. Bu önceden derlenmiş üst bilgi ile derleme herhangi bir kaynak dosyayı nesne modülü ve kitaplık hata ayıklama bilgilerini içerecek şekilde bağlayıcı neden olan belirtilen simgeyi gösterir.
