---
title: LIB giriş dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 952c3345234192e3798fea483d527cd3afec4bff
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702474"
---
# <a name="lib-input-files"></a>LIB Giriş Dosyaları

LIB tarafından beklenen giriş dosyaları aşağıdaki tabloda gösterildiği gibi çünkü kullanılıyor, modunu bağlıdır.

|Mod|Giriş|
|----------|-----------|
|Varsayılan (oluşturmak veya bir kitaplık değiştirme)|COFF nesne (.obj) dosyaları, COFF kitaplık (.lib), 32-bit nesne modeli biçimi (OMF) nesne (.obj) dosyaları|
|/ Extract ile bir üyesini ayıklama|COFF kitaplık (.lib)|
|Bir dışarı aktarma dosyası oluşturup ile/def kitaplığı içeri aktarma|Modül-tanımlama (.def) dosyası, COFF nesne (.obj) dosyaları, COFF kitaplık (.lib), 32-bit OMF nesne (.obj) dosyaları|

> [!NOTE]
>  OMF kitaplıkları LIB 16-bit sürümü tarafından oluşturulmuş, LIB'ın 32 bit sürümü için giriş olarak kullanılamaz.

## <a name="see-also"></a>Ayrıca Bkz.

[LIB'e Genel Bakış](../../build/reference/overview-of-lib.md)