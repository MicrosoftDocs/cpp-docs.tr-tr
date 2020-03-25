---
title: Bağlayıcı Araçları Hatası LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: 0c531f70f98a017e8b75cceddc684f99d33bc554
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194608"
---
# <a name="linker-tools-error-lnk2027"></a>Bağlayıcı Araçları Hatası LNK2027

çözümlenmemiş modül başvurusu ' Module '

Bağlayıcıya geçirilen bir dosya, **/ASSEMBLYMODULE** ile belirtilmeyen veya doğrudan bağlayıcıya geçilen bir modüle bağımlılığı vardır.

LNK2027 çözümlemek için aşağıdakilerden birini yapın:

- Modül bağımlılığı olan dosyayı bağlayıcıya geçirmeyin.

- **/ASSEMBLYMODULE**ile modülü belirtin.

- Modül güvenli bir. netmodule ise, modülü doğrudan bağlayıcıya geçirin.

Daha fazla bilgi için, bkz. [/ASSEMBLYMODULE (DERLEMEYE MSIL Modülü ekleme)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) ve [. netmodule dosyaları bağlayıcı girişi olarak](../../build/reference/netmodule-files-as-linker-input.md).
