---
title: LIB Giriş Dosyaları
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: 885d03e74c7acff54e527c2dbad38de055913b5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503339"
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