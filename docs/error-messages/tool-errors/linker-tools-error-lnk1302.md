---
title: Bağlayıcı Araçları Hatası LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: 8323fa234851ce3ba12083adb74d5ee0fba0ac69
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194934"
---
# <a name="linker-tools-error-lnk1302"></a>Bağlayıcı Araçları Hatası LNK1302

yalnızca güvenli. netmodules bağlamayı destekle; File. netmodule bağlantısı kurulamıyor

Bir. netmodule ( **/ln**ile derlenen), BIR kullanıcı MSIL bağlamayı çağırma girişiminde bir bağlayıcıya geçildi.  C++ **/Clr: Safe**ile derlenirse, bir modül MSIL bağlama için geçerlidir.

Bu hatayı düzeltmek için, MSIL bağlamayı etkinleştirmek üzere **/clr: Safe** ile derleyin veya **/clr** veya **/clr: Pure** . obj dosyasını modül yerine bağlayıcıya geçirin.

Daha fazla bilgi için bkz.

- [/LN (MSIL Modülü Oluştur)](../../build/reference/ln-create-msil-module.md)

- [Bağlayıcı Girişi olarak .netmodule Dosyaları](../../build/reference/netmodule-files-as-linker-input.md)
