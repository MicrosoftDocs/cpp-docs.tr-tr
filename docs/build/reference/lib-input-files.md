---
title: LIB Giriş Dosyaları
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: fb0095bd9e8699fbc9a1a144833d12d2cf4a1f83
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423098"
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

## <a name="see-also"></a>Ayrıca bkz.

[LIB'e Genel Bakış](../../build/reference/overview-of-lib.md)
