---
title: inject_statement içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: 25dee621ff8af2c9a39e605b9da2c29d80f9570a
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220997"
---
# <a name="inject_statement-import-attribute"></a>inject_statement içeri aktarma özniteliği

**C++Belirli**

Bağımsız değişkenini tür kitaplığı üstbilgisine kaynak metin olarak ekler.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **inject_statement (** "*kaynak-metin*" **)**

### <a name="parameters"></a>Parametreler

*kaynak-metin*\
Tür kitaplığı üstbilgi dosyasına eklenecek kaynak metin.

## <a name="remarks"></a>Açıklamalar

Metin, üstbilgi dosyasındaki *tür kitaplığı* içeriğini sarmalayan ad alanı bildiriminin başlangıcına yerleştirilir.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
