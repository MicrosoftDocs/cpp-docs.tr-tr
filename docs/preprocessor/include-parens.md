---
description: ': İnclude () Import özniteliği hakkında daha fazla bilgi'
title: Include () Import özniteliği
ms.date: 08/29/2019
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: e1164526f95bf1b916cd684a892fbef35027f984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236483"
---
# <a name="include-import-attribute"></a>Include () Import özniteliği

**C++ özel**

Otomatik dışlamayı devre dışı bırakır.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **ekleme ("**_name1_**"** [__, "__*AD2*__"__ ...] __)__

### <a name="parameters"></a>Parametreler

*Name1*\
Zorla eklenecek ilk öğe.

*Name2*\
Zorla dahil edilecek ikinci öğe (gerekirse).

## <a name="remarks"></a>Açıklamalar

Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import` Bu tür öğeleri otomatik olarak dışlayarak birden çok tanım hatasını önlemenize çalışır. Bazı öğeler otomatik olarak dışlanmazsa, [Derleyici Uyarısı (düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)' u görebilirsiniz. Otomatik dışlamayı devre dışı bırakmak için bu özniteliği kullanabilirsiniz. Bu öznitelik, bir tür kitaplığı öğesinin dahil edilecek her adı için bir tane olmak üzere herhangi bir sayıda bağımsız değişken alabilir.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
