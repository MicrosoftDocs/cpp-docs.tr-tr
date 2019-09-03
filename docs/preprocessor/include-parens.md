---
title: Include () Import özniteliği
ms.date: 08/29/2019
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 39ab63525b2b83781cbcaf86a61742c5fb767b72
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218873"
---
# <a name="include-import-attribute"></a>Include () Import özniteliği

**C++Belirli**

Otomatik dışlamayı devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **dahil et ("** _name1_ **"** [ __, "__ *AD2* __"__ ...] __)__

### <a name="parameters"></a>Parametreler

*Name1*\
Zorla eklenecek ilk öğe.

*Name2*\
Zorla dahil edilecek ikinci öğe (gerekirse).

## <a name="remarks"></a>Açıklamalar

Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import`Bu tür öğeleri otomatik olarak dışlayarak birden çok tanım hatasını önlemenize çalışır. Bazı öğeler otomatik olarak dışlanmazsa, [Derleyici Uyarısı (düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)' u görebilirsiniz. Otomatik dışlamayı devre dışı bırakmak için bu özniteliği kullanabilirsiniz. Bu öznitelik, bir tür kitaplığı öğesinin dahil edilecek her adı için bir tane olmak üzere herhangi bir sayıda bağımsız değişken alabilir.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
