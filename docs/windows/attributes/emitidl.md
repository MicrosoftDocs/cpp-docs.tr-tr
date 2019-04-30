---
title: emitidl (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.emitidl
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
ms.openlocfilehash: 6c4055e0f14bced1e5047fc502a4bf274126f804
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409661"
---
# <a name="emitidl"></a>emitidl

Tüm sonraki IDL öznitelikleri işlenir ve oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>Parametreler

*durumu*<br/>
Bu değerlerden biri: `true`, `false`, `forced`, `restricted`, `push`, veya `pop`.

- Varsa `true`, bir kaynak kodu dosyasında karşılaşılan kategori IDL öznitelikleri oluşturulan .idl dosyasında yerleştirilir. İçin varsayılan ayar budur **emitidl**.

- Varsa `false`, bir kaynak kodu dosyasında karşılaşılan kategori IDL öznitelikleri oluşturulan .idl dosyasına yerleştirilmez.

- Varsa `restricted`, IDL öznitelikleri dosyasındaki olmasını sağlayan bir [Modülü](module-cpp.md) özniteliği. Derleyici bir .idl dosyası oluşturmaz.

- Varsa `forced`, bir sonraki geçersiz kılar `restricted` sahip için dosya gerektirmiyor özniteliği, bir `module` IDL varsa özniteliği dosyasında öznitelikleri.

- `push` Geçerli kaydetmenizi sağlayan **emitidl** ayarları bir iç **emitidl** yığını ve `pop` , ayarlamanıza imkan sağlar **emitidl** ne olursa olsun değer iç üstünde olduğu için **emitidl** yığını.

`defaultimports=`*Boole* \(isteğe bağlı)

- Varsa *Boole* olduğu **true**, docobj.idl oluşturulan .idl dosyasına aktarılır. Ayrıca, bir .idl dosyası ile aynı adı taşıyan bir .h dosyası varsa `#include` kaynak kodu .h dosyası ile aynı dizinde bulunan ve ardından söz konusu .idl dosyası için bir içeri aktarma deyimi oluşturulan .idl dosyası içerir.

- Varsa *Boole* olduğu **false**, docobj.idl oluşturulan .idl dosyasına alınmadı. .İdl dosyaları ile açıkça içeri aktarmanız gerekir [alma](import.md).

## <a name="remarks"></a>Açıklamalar

Sonra **emitidl** C++ öznitelik, bir kaynak kodu dosyasında karşılaşıldığında, IDL kategori öznitelikler oluşturulan .idl dosyasında yerleştirilir. Yoksa hiçbir **emitidl** özniteliği, kaynak kod dosyasında IDL öznitelikleri oluşturulan .idl dosyasının çıkarılır.

Birden çok olması mümkündür **emitidl** kaynak kodu dosyasında öznitelikleri. Varsa `[emitidl(false)];` sonraki olmadan bir dosya ile karşılaşılırsa `[emitidl(true)];`, sonra oluşturulan .idl dosyasına özniteliklere işlenir.

Derleyici, yeni bir dosya karşılaştığında her zaman **emitidl** örtük olarak ayarlandığında **true**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)
