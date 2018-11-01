---
title: Bağlayıcı Araçları Hatası LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: e74912780bab3056ead36ae3705f0910805228e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545905"
---
# <a name="linker-tools-error-lnk2027"></a>Bağlayıcı Araçları Hatası LNK2027

Çözümlenmemiş modül başvurusu 'module'

Bağlayıcı için geçirilen dosya tipleri ile belirtilen bir modülde bağımlılığa sahip **assemblymodule** ya da doğrudan bağlayıcıya geçirildi.

LNK2027 çözümlemek için aşağıdakilerden birini yapın:

- Bağlayıcı için modül bağımlılığının dosya geçirmeyin.

- Modülüyle belirtin **assemblymodule**.

- Güvenli bir .netmodule modülü ise modülü bağlayıcıya doğrudan geçirin.

Daha fazla bilgi için [assemblymodule (derlemeye MSIL Modülü Ekle)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) ve [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).