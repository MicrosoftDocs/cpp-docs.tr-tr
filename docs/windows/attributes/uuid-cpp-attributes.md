---
title: uuid (C++ Öznitelikleri)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: 72d18eb50f8d85fb10d5af3ffce08c5b74947531
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222101"
---
# <a name="uuid-c-attributes"></a>uuid (C++ Öznitelikleri)

Bir sınıf veya arabirim için benzersiz KIMLIĞI belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ uuid( "uuid" ) ]
```

### <a name="parameters"></a>Parametreler

*uuid*<br/>
128 bit, benzersiz bir tanımlayıcı.

## <a name="remarks"></a>Açıklamalar

Bir arabirimin veya sınıfın tanımı `uuid` C++ özniteliğini belirtmezse, Microsoft C++ derleyicisi bir tane sağlar. Bir belirttiğinizde `uuid` , tırnak işaretleri dahil etmeniz gerekir.

Belirtmezseniz `uuid` , derleyici bir makinedeki farklı öznitelik projelerinde aynı ada sahip arabirimler veya sınıflar için aynı GUID 'i oluşturur.

Uuidgen.exe veya Guidgen.exe, kendi benzersiz kimliklerinizi oluşturmak için kullanabilirsiniz. (Bu araçlardan birini çalıştırmak için **Başlat** ' a tıklayın ve menüden **Çalıştır** ' a tıklayın. Ardından gerekli aracın adını girin.)

Aynı zamanda ATL kullanmayan bir projede kullanıldığında, `uuid` özniteliği belirtmek [UUID](../../cpp/uuid-cpp.md) değiştiricisini belirtmeyle aynıdır **`__declspec`** . `uuid`Bir sınıfı almak için [__uuidof](../../cpp/uuidof-operator.md) kullanabilirsiniz

## <a name="example"></a>Örnek

Örnek kullanımı için [bağlanabilir](bindable.md) örneğe bakın `uuid` .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|`class`, `struct`, `interface`, `union`, `enum`|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/win32/Midl/uuid)
