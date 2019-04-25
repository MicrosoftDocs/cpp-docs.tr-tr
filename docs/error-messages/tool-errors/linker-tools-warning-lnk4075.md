---
title: Bağlayıcı Araçları Uyarısı LNK4075
ms.date: 11/04/2016
f1_keywords:
- LNK4075
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
ms.openlocfilehash: bf22e7c78dce6949c357d7ad4a0c76209c88eef3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186911"
---
# <a name="linker-tools-warning-lnk4075"></a>Bağlayıcı Araçları Uyarısı LNK4075

"Seçenek2" belirtimi nedeniyle "Seçenek1" yoksayılıyor

İkinci seçenek, ilk geçersiz kılar.

Birbirini dışlayan bağlayıcı seçenekleri belirtilir.  Bağlayıcı seçenekleri inceleyin.  Bağlayıcı seçenekleri Burada belirtilen nasıl projenizi oluşturma bağlıdır.

- Geliştirme ortamında geliştiriyorsanız, projeniz için bağlayıcı özellik sayfaları bakın ve hem bağlayıcı seçenekleri Burada belirtilen bakın.  Bkz: [derleyici ayarlayın ve derleme özellikleri](../../build/working-with-project-properties.md) daha fazla bilgi için.

- Komut satırında derleme yaparsanız, var. belirtilen bağlayıcı seçeneklerine bakın.

- Derleme betikleri ile yapılandırdıysanız, bu bağlayıcı seçenekleri Burada belirtilen görmek için betiklerinizi arayın.

Birbirini dışlayan bağlayıcı seçenekleri Burada belirtilen bulduğunuzda, bağlayıcı seçenekleri birini kaldırın.

Belirli bazı örnekler:

- İle derlenmiş bir modül bağlarsanız **/zi**, bir iç bağlayıcı seçeneği olduğu anlamına gelir/edıtandcontınue ve/OPT: ref, / OPT: ICF veya/Incremental: No, derlenen bir modül yok/edıtandcontınue yaptığından çağrılır, olur LNK4075 alın.  Bkz: [/z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md) daha fazla bilgi için.