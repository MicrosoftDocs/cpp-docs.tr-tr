---
description: 'Daha fazla bilgi edinin: içeri aktarma özniteliği Dışla'
title: İçeri aktarma özniteliğini Dışla
ms.date: 08/29/2019
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: e856544f812fd5d0b14676beb8423c4350e40da1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269321"
---
# <a name="exclude-import-attribute"></a>İçeri aktarma özniteliğini Dışla

**C++ özel**

Öğeleri, oluşturulan tür kitaplığı üstbilgi dosyalarından çıkarır.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **dışla (** "*name1*" [ **,** "*AD2*"...] **)**

### <a name="parameters"></a>Parametreler

*Name1*\
Çıkarılacak ilk öğe.

*Name2*\
Seçim Gerekirse dışarıda bırakılacak ikinci ve sonraki öğeler.

## <a name="remarks"></a>Açıklamalar

Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. Bu öznitelik, her biri dışlanacak en üst düzey bir tür kitaplığı öğesi olan herhangi bir sayıda bağımsız değişken alabilir.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
