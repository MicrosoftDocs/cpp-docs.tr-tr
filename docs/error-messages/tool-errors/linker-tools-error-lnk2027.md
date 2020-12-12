---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK2027'
title: Bağlayıcı Araçları Hatası LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: 006ca3b0c9d0ef85f118db9b562e8228c7cad238
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275769"
---
# <a name="linker-tools-error-lnk2027"></a>Bağlayıcı Araçları Hatası LNK2027

çözümlenmemiş modül başvurusu ' Module '

Bağlayıcıya geçirilen bir dosya, **/ASSEMBLYMODULE** ile belirtilmeyen veya doğrudan bağlayıcıya geçilen bir modüle bağımlılığı vardır.

LNK2027 çözümlemek için aşağıdakilerden birini yapın:

- Modül bağımlılığı olan dosyayı bağlayıcıya geçirmeyin.

- **/ASSEMBLYMODULE** ile modülü belirtin.

- Modül güvenli bir. netmodule ise, modülü doğrudan bağlayıcıya geçirin.

Daha fazla bilgi için, bkz. [/ASSEMBLYMODULE (DERLEMEYE MSIL Modülü ekleme)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) ve [. netmodule dosyaları bağlayıcı girişi olarak](../../build/reference/netmodule-files-as-linker-input.md).
