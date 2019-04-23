---
title: Yerel (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: 678968bb7b0f2e7af94124bea5b0967df27e43f7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033076"
---
# <a name="local-c"></a>yerel (C++)

Arabirimi başlığı kullanıldığında, MIDL derleyici üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
[local]
```

## <a name="remarks"></a>Açıklamalar

**Yerel** C++ özniteliği ile aynı işlevlere sahip [yerel](/windows/desktop/Midl/local) MIDL özniteliği.

## <a name="example"></a>Örnek

Bkz: [call_as](call-as.md) nasıl kullanılacağına ilişkin bir örnek **yerel**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**arabirimi**, arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|`dispinterface`|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[call_as](call-as.md)