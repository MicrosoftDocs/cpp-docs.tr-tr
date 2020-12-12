---
description: 'Daha fazla bilgi için: LıB giriş dosyaları'
title: LIB Giriş Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: f40cba91f0772e0073daca20a8f2093f3eec8aec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199557"
---
# <a name="lib-input-files"></a>LIB Giriş Dosyaları

LıB tarafından beklenen giriş dosyaları, aşağıdaki tabloda gösterildiği gibi, kullanıldığı moda bağlıdır.

|Mod|Giriş|
|----------|-----------|
|Varsayılan (bir kitaplığı oluşturma veya değiştirme)|COFF nesne (. obj) dosyaları, COFF kitaplıkları (. lib), 32-bit nesne modeli biçimi (OMF) nesne (. obj) dosyaları|
|/EXTRACT ile üye ayıklama|COFF kitaplığı (. lib)|
|Dışa aktarma dosyası oluşturma ve kitaplığı/DEF ile içeri aktarma|Modül tanım (. def) dosyası, COFF nesne (. obj) dosyaları, COFF kitaplıkları (. lib), 32-bit OMF nesne (. obj) dosyaları|

> [!NOTE]
> LIB 'in 16 bit sürümü tarafından oluşturulan OMF kitaplıkları, LıB 'in 32 bitlik sürümüne giriş olarak kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[LIB'e Genel Bakış](overview-of-lib.md)
