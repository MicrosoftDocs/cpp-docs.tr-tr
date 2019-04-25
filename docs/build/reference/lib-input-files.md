---
title: LIB Giriş Dosyaları
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: 648871464dbc99972b8ca40579046347727e81cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269394"
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

[LIB'e Genel Bakış](overview-of-lib.md)
