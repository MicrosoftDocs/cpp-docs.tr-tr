---
title: Bağlayıcı Araçları Hatası LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: e74912780bab3056ead36ae3705f0910805228e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299016"
---
# <a name="linker-tools-error-lnk2027"></a>Bağlayıcı Araçları Hatası LNK2027

Çözümlenmemiş modül başvurusu 'module'

Bağlayıcı için geçirilen dosya tipleri ile belirtilen bir modülde bağımlılığa sahip **assemblymodule** ya da doğrudan bağlayıcıya geçirildi.

LNK2027 çözümlemek için aşağıdakilerden birini yapın:

- Bağlayıcı için modül bağımlılığının dosya geçirmeyin.

- Modülüyle belirtin **assemblymodule**.

- Güvenli bir .netmodule modülü ise modülü bağlayıcıya doğrudan geçirin.

Daha fazla bilgi için [assemblymodule (derlemeye MSIL Modülü Ekle)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) ve [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).