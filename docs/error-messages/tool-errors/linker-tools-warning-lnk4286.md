---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4286'
title: Bağlayıcı Araçları Uyarısı LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: 6a1e397967857ae3f982bf8f5e55f4bf74c9abe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244452"
---
# <a name="linker-tools-warning-lnk4286"></a>Bağlayıcı Araçları Uyarısı LNK4286

> '*filename_1. obj*' içinde tanımlanan '*symbol*' sembolü '*filename_2. obj*' tarafından içeri aktarıldı

sembol aynı görüntüde *filename_1. obj* nesne dosyasında tanımlanmış olsa da *sembol* için [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) belirtildi. `__declspec(dllimport)`Bu uyarıyı çözmek için değiştiricisini kaldırın.

## <a name="remarks"></a>Açıklamalar

Uyarı LNK4286, [bağlayıcı araçlarının uyarı LNK4217](linker-tools-warning-lnk4217.md)'in daha genel bir sürümüdür. Bağlayıcı, simgenin hangi nesne dosyasına başvurduğunu ancak işlevin olmadığını bildirebileceği halde bir uyarı LNK4286 oluşturur.

LNK4286 çözümlemek için, `__declspec(dllimport)` bildirim değiştiricisini *filename_2. obj* içinde başvurulan *simgenin* ileri bildiriminden kaldırın.

Son oluşturulan kod doğru şekilde davransa da, içeri aktarılan bir işlevi çağırmak için oluşturulan kod, işlevi doğrudan çağırmaktan daha az verimlidir. Bu uyarı [/clr](../../build/reference/clr-common-language-runtime-compilation.md) seçeneğini kullanarak derlerken görünmez.

Verileri içeri ve dışarı aktarma bildirimleri hakkında daha fazla bilgi için bkz. [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları uyarısı LNK4049](linker-tools-warning-lnk4049.md) \
[Bağlayıcı Araçları uyarısı LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
