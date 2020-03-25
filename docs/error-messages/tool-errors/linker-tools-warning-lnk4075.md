---
title: Bağlayıcı Araçları Uyarısı LNK4075
ms.date: 11/04/2016
f1_keywords:
- LNK4075
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
ms.openlocfilehash: e4a385b9559e2f54e81bda76e6dd13505e978a74
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183494"
---
# <a name="linker-tools-warning-lnk4075"></a>Bağlayıcı Araçları Uyarısı LNK4075

"Seçenek2" belirtimi nedeniyle "Seçenek1" yoksayılıyor

İkinci seçenek birincisini geçersiz kılar.

Birbirini dışlayan bağlayıcı seçenekleri belirtilmekte.  Bağlayıcı seçeneklerinizi inceleyin.  Bağlayıcı seçeneklerinin belirtildiği yer, projenizi oluşturma şeklinize bağlıdır.

- Geliştirme ortamında oluşturuyorsanız, projeniz için bağlayıcı özelliği sayfalarına bakın ve her iki bağlayıcı seçeneğinin nerede belirtilmekte olduğunu görün.  Daha fazla bilgi için bkz. [derleyici ve derleme özelliklerini ayarlama](../../build/working-with-project-properties.md) .

- Komut satırında derleme yaparsanız, burada belirtilen bağlayıcı seçeneklerine bakın.

- Derleme betikleri ile derleme yaparsanız, bu bağlayıcı seçeneklerinin nerede belirtilmekte olduğunu görmek için betiklerinizde arama yapın.

Birbirini dışlayan bağlayıcı seçeneklerinin belirtildiği yeri bulduğunuzda, bağlayıcı seçeneklerinden birini kaldırın.

Bazı özel örnekler:

- /EDITANDCONTINUE adlı bir iç bağlayıcı seçeneğinin yanı sıra/DıDıTEM: REF,/OPT: ICF veya/ıNCRELADıAL: NO ile derlenen bir modül olan **/Zi**ile derlenen bir modülü BAĞLARSANıZ, LNK4075 alırsınız.  Daha fazla bilgi için bkz. [/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md) .
