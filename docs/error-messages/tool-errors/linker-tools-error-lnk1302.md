---
title: Bağlayıcı Araçları Hatası LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: c3b1117b31db4759b385943323a581da7a58f0c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491084"
---
# <a name="linker-tools-error-lnk1302"></a>Bağlayıcı Araçları Hatası LNK1302

yalnızca güvenli. netmodule'leri bağlamayı destekle; dosya .netmodule bağlanamıyor

.Netmodule (ile derlenmiş **/LN**) bağlayıcıya MSIL bağlantılandırma çağırmak için bir kullanıcı girişimi geçirildi.  MSIL ile derlenmişse bağlamak için geçerli bir C++ modülünün **/CLR: safe**.

Bu hatayı düzeltmek için derlemek **/CLR: safe** MSIL bağlamayı etkinleştir veya geçirmek için **/CLR** veya **/CLR: pure** modül yerine bağlayıcı .obj dosyasına.

Daha fazla bilgi için bkz.

- [/LN (MSIL Modülü Oluştur)](../../build/reference/ln-create-msil-module.md)

- [Bağlayıcı Girişi olarak .netmodule Dosyaları](../../build/reference/netmodule-files-as-linker-input.md)