---
title: Bağlayıcı Araçları Uyarısı LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: d0205ba065f6e410383c38a0f1c2eaa0da55fe93
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173874"
---
# <a name="linker-tools-warning-lnk4286"></a>Bağlayıcı Araçları Uyarısı LNK4286

> '*filename_1. obj*' içinde tanımlanan '*symbol*' sembolü '*filename_2. obj*' tarafından içeri aktarıldı

sembol aynı görüntüde *filename_1. obj* nesne dosyasında tanımlanmış olsa da *sembol* için [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) belirtildi. Bu uyarıyı çözmek için `__declspec(dllimport)` değiştiricisini kaldırın.

## <a name="remarks"></a>Açıklamalar

Uyarı LNK4286, [bağlayıcı araçlarının uyarı LNK4217](linker-tools-warning-lnk4217.md)'in daha genel bir sürümüdür. Bağlayıcı, simgenin hangi nesne dosyasına başvurduğunu ancak işlevin olmadığını bildirebileceği halde bir uyarı LNK4286 oluşturur.

LNK4286 çözümlemek için `__declspec(dllimport)` bildirim değiştiricisini *filename_2. obj*içinde başvurulan *simgenin* ileri bildiriminden kaldırın.

Son oluşturulan kod doğru şekilde davransa da, içeri aktarılan bir işlevi çağırmak için oluşturulan kod, işlevi doğrudan çağırmaktan daha az verimlidir. Bu uyarı [/clr](../../build/reference/clr-common-language-runtime-compilation.md) seçeneğini kullanarak derlerken görünmez.

Verileri içeri ve dışarı aktarma bildirimleri hakkında daha fazla bilgi için bkz. [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı araçları uyarısı LNK4049](linker-tools-warning-lnk4049.md) \
[Bağlayıcı araçları uyarısı LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
