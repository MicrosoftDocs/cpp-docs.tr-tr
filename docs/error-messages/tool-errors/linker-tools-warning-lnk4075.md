---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4075'
title: Bağlayıcı Araçları Uyarısı LNK4075
ms.date: 11/04/2016
f1_keywords:
- LNK4075
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
ms.openlocfilehash: d7883573271522857b34b3aac81bf45029e540ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210168"
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

- /EDITANDCONTINUE adlı bir iç bağlayıcı seçeneğinin yanı sıra/DıDıTEM: REF,/OPT: ICF veya/ıNCRELADıAL: NO ile derlenen bir modül olan **/Zi** ile derlenen bir modülü BAĞLARSANıZ, LNK4075 alırsınız.  Daha fazla bilgi için bkz. [/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md) .
