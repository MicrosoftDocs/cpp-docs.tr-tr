---
title: Bağlayıcı araçları hatası LNK1302 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc85b37d58e12602c02c2207c1f38bda9344e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045516"
---
# <a name="linker-tools-error-lnk1302"></a>Bağlayıcı Araçları Hatası LNK1302

yalnızca güvenli. netmodule'leri bağlamayı destekle; dosya .netmodule bağlanamıyor

.Netmodule (ile derlenmiş **/LN**) bağlayıcıya MSIL bağlantılandırma çağırmak için bir kullanıcı girişimi geçirildi.  MSIL ile derlenmişse bağlamak için geçerli bir C++ modülünün **/CLR: safe**.

Bu hatayı düzeltmek için derlemek **/CLR: safe** MSIL bağlamayı etkinleştir veya geçirmek için **/CLR** veya **/CLR: pure** modül yerine bağlayıcı .obj dosyasına.

Daha fazla bilgi için bkz.

- [/LN (MSIL Modülü Oluştur)](../../build/reference/ln-create-msil-module.md)

- [Bağlayıcı Girişi olarak .netmodule Dosyaları](../../build/reference/netmodule-files-as-linker-input.md)