---
title: İçeri aktarma özniteliğini Dışla
ms.date: 08/29/2019
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: 6a3625ee0dd44f3e2731e1240fea5f3dd4ed109e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218724"
---
# <a name="exclude-import-attribute"></a>İçeri aktarma özniteliğini Dışla

**C++Belirli**

Öğeleri, oluşturulan tür kitaplığı üstbilgi dosyalarından çıkarır.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **exclude (** "*name1*" [ **,** "*AD2*"...] **)**

### <a name="parameters"></a>Parametreler

*Name1*\
Çıkarılacak ilk öğe.

*Name2*\
Seçim Gerekirse dışarıda bırakılacak ikinci ve sonraki öğeler.

## <a name="remarks"></a>Açıklamalar

Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. Bu öznitelik, her biri dışlanacak en üst düzey bir tür kitaplığı öğesi olan herhangi bir sayıda bağımsız değişken alabilir.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
