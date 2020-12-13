---
description: 'Hakkında daha fazla bilgi edinin: emitidl'
title: emitidl (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.emitidl
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
ms.openlocfilehash: 21c4f7fc067eb37b8816bdedd1f338908950566e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337793"
---
# <a name="emitidl"></a>emitidl

Sonraki tüm IDL özniteliklerinin işlenip işlenmeyeceğini ve oluşturulan. IDL dosyasına yerleştirilip yerleştirilmeyeceğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
Şu olası değerlerden biri: **`true`** , **`false`** ,, `forced` `restricted` , `push` veya `pop` .

- **`true`** Bir kaynak kod dosyasında karşılaşılan IDL kategorisi öznitelikleri oluşturulan. IDL dosyasına yerleştirilir. Bu, **emitidl** için varsayılan ayardır.

- **`false`** Bir kaynak kod dosyasında karşılaşılan IDL kategorisi öznitelikleri oluşturulan. IDL dosyasına yerleştirilmez.

- İse `restricted` , IDL özniteliklerinin bir [Modül](module-cpp.md) özniteliği olmadan dosyada olmasını sağlar. Derleyici bir. IDL dosyası oluşturmaz.

- İse `forced` , `restricted` dosyada IDL öznitelikleri varsa dosyanın bir özniteliğe sahip olmasını gerektiren sonraki bir özniteliği geçersiz kılar `module` .

- `push` geçerli **emitidl** ayarlarını bir iç **emitidl** yığınına kaydetmenizi sağlar ve `pop` **emitidl** , iç **emitidl** yığınının en üstünde olan herhangi bir değere ayarlamanıza olanak sağlar.

`defaultimports=`*Boole değeri* \( seçim

- *Boolean* ise **`true`** docobj. IDL dosyası oluşturulan. IDL dosyasına aktarılır. Ayrıca, kaynak kodunuzda kullandığınız bir. h dosyası ile aynı ada sahip bir. IDL dosyası `#include` . h dosyasıyla aynı dizinde bulunursa, oluşturulan. IDL dosyası bu. IDL dosyası için bir içeri aktarma ekstresi içerir.

- *Boolean* ise **`false`** docobj. IDL dosyası oluşturulan. IDL dosyasına aktarılmaz. [İmport](import.md)ile. IDL dosyalarını açıkça içeri aktarmanız gerekir.

## <a name="remarks"></a>Açıklamalar

Kaynak kod dosyasında **emitidl** C++ özniteliğiyle KARŞıLAŞıLDıĞıNDA, IDL kategorisi öznitelikleri oluşturulan. IDL dosyasına yerleştirilir. **Emitidl** özniteliği yoksa, kaynak kod dosyasındaki IDL öznitelikleri oluşturulan. IDL dosyasına çıktıdır.

Bir kaynak kod dosyasında birden çok **emitidl** özniteliği olması mümkündür. `[emitidl(false)];`Bundan sonra bir dosyada karşılaşılırsa `[emitidl(true)];` , oluşturulan. IDL dosyasına hiçbir öznitelik işlenmeyecektir.

Derleyici yeni bir dosya ile karşılaştığında, **emitidl** örtülü olarak olarak ayarlanır **`true`** .

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)
