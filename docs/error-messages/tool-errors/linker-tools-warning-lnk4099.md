---
title: Bağlayıcı Araçları Uyarısı LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: dcf4d44c3a0b5b10035af763040c2912afc8c6f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442183"
---
# <a name="linker-tools-warning-lnk4099"></a>Bağlayıcı Araçları Uyarısı LNK4099

PDB 'filename', 'nesne/Kitaplık' veya 'path';'konumunda bulunamadı Nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

Bağlayıcı, .pdb dosyasını bulamadı. Dosyayı içeren dizine kopyalayın `object/library`.

Nesne dosyası ile ilişkili .pdb dosyasının adını bulmak için:

1. Bir nesne dosyası kitaplığı ile ayıklamak [LIB](../../build/reference/lib-reference.md) **/ayıklayın:**`objectname`**.obj** `xyz` **.lib**.

1. İle .pdb dosyasının yolunu denetleyin **dumpbin /section:.debug$ T /rawdata** `objectname` **.obj**.

İle derleme [/z7](../../build/reference/z7-zi-zi-debug-information-format.md), pdb kaldırın veya kullanılabilir gerekmez [/DEBUG](../../build/reference/debug-generate-debug-info.md) bağlandığınız nesneler için .pdb dosyası yoksa bağlayıcı seçeneği.