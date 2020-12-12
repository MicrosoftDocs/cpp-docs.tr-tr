---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1302'
title: Bağlayıcı Araçları Hatası LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: 33e9a406cde7910c7340fdfe256711c47eee45cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193701"
---
# <a name="linker-tools-error-lnk1302"></a>Bağlayıcı Araçları Hatası LNK1302

yalnızca güvenli. netmodules bağlamayı destekle; File. netmodule bağlantısı kurulamıyor

Bir. netmodule ( **/ln** ile derlenen), BIR kullanıcı MSIL bağlamayı çağırma girişiminde bir bağlayıcıya geçildi.  C++ modülü **/clr: Safe** ile DERLENMIŞSE MSIL bağlama için geçerlidir.

Bu hatayı düzeltmek için, MSIL bağlamayı etkinleştirmek üzere **/clr: Safe** ile derleyin veya **/clr** veya **/clr: Pure** . obj dosyasını modül yerine bağlayıcıya geçirin.

Daha fazla bilgi için bkz.

- [/LN (MSIL Modülü Oluştur)](../../build/reference/ln-create-msil-module.md)

- [Bağlayıcı girişi olarak. netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md)
