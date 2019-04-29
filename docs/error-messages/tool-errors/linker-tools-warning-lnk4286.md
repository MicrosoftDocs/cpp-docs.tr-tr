---
title: Bağlayıcı Araçları Uyarısı LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: 43ed18808ba5ce632dd7dc7095f7bc30e4497ec9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352443"
---
# <a name="linker-tools-warning-lnk4286"></a>Bağlayıcı Araçları Uyarısı LNK4286

> Sembol '*sembol*'içinde tanımlanan'*filename_1.obj*'tarafından alınan'*filename_2.obj*'

[__declspec(dllimport)](../../cpp/dllexport-dllimport.md) için belirtilen *sembol* sembolü nesne dosyasında tanımlanan olsa bile *filename_1.obj* aynı görüntüde. Kaldırma `__declspec(dllimport)` bu uyarıyı çözmek için değiştiricisi.

## <a name="remarks"></a>Açıklamalar

Uyarı LNK4286 daha genel bir sürümü olan [Bağlayıcı araçları uyarısı LNK4217](linker-tools-warning-lnk4217.md). Hangi nesne dosyası sembole başvurulduğunda ancak hangi işlevi söyleyebilirsiniz uyarı LNK4286 bağlayıcı oluşturur.

LNK4286 çözmek için kaldırma `__declspec(dllimport)` İleri dönük bildiriminin öğesinden bildirim değiştirici *sembol* bulunulan *filename_2.obj*.

Son oluşturulan kodun doğru şekilde davranır ancak, içeri aktarılan bir işlevi çağırmak için oluşturulan kodu işlevi doğrudan çağırma değerinden daha az verimlidir. Bu uyarı kullanarak derleme yaptığınızda görünmez [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) seçeneği.

Hakkında daha fazla bilgi almak ve veri bildirimlerini dışarı aktarmak için bkz. [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı araçları uyarısı LNK4049](linker-tools-warning-lnk4049.md) \
[Bağlayıcı araçları uyarısı LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)