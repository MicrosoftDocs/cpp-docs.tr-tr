---
title: LIB Giriş Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: de81f79eecf3fc73c02894747f4b97cb107cf892
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328222"
---
# <a name="lib-input-files"></a>LIB Giriş Dosyaları

LIB tarafından beklenen giriş dosyaları, aşağıdaki tabloda gösterildiği gibi, kullanıldığı moda bağlıdır.

|Mod|Girdi|
|----------|-----------|
|Varsayılan (kitaplık oluşturma veya değiştirme)|COFF nesnesi (.obj) dosyaları, COFF kitaplıkları (.lib), 32 bit Nesne Modeli Biçimi (OMF) nesnesi (.obj) dosyaları|
|/EXTRACT ile üye ayıklama|COFF kitaplığı (.lib)|
|/DEF ile bir dışa aktarma dosyası oluşturma ve kitaplık alma|Modül tanımı (.def) dosyası, COFF nesnesi (.obj) dosyaları, COFF kitaplıkları (.lib), 32-bit OMF nesnesi (.obj) dosyaları|

> [!NOTE]
> LIB'in 16 bit sürümü tarafından oluşturulan OMF kitaplıkları LIB'in 32 bit sürümüne giriş olarak kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[LIB'e Genel Bakış](overview-of-lib.md)
