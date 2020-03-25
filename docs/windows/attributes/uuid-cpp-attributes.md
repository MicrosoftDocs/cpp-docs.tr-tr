---
title: uuid (C++ Öznitelikleri)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: c507a9ae42afc5081c290d38464aa7f24c277d15
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166126"
---
# <a name="uuid-c-attributes"></a>uuid (C++ Öznitelikleri)

Bir sınıf veya arabirim için benzersiz KIMLIĞI belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ uuid(
   "uuid"
) ]
```

### <a name="parameters"></a>Parametreler

*uuid*<br/>
128 bit, benzersiz bir tanımlayıcı.

## <a name="remarks"></a>Açıklamalar

Bir arabirimin veya sınıfın tanımı **UUID** C++ özniteliğini belirtmezse, Microsoft C++ derleyicisi bir tane sağlayacaktır. Bir **UUID**belirttiğinizde, tırnak işaretleri dahil etmeniz gerekir.

**UUID**belirtmezseniz, derleyici bir makinedeki farklı öznitelik projelerinde aynı ada sahip arabirimler veya sınıflar IÇIN aynı GUID 'i oluşturur.

Kendi benzersiz kimliklerinizi oluşturmak için Uuidgen. exe veya GUIDgen. exe kullanabilirsiniz. (Bu araçlardan birini çalıştırmak için **Başlat** ' a tıklayın ve menüden **Çalıştır** ' a tıklayın. Ardından gerekli aracın adını girin.)

ATL kullanmayan bir projede kullanıldığında, **UUID** özniteliği belirtildiğinde [UUID](../../cpp/uuid-cpp.md) **__declspec** değiştiricisi belirtilerek aynı olur. Bir sınıfın **UUID** 'sini almak için [__uuidof](../../cpp/uuidof-operator.md) kullanabilirsiniz

## <a name="example"></a>Örnek

**UUID**'nin örnek bir kullanımı için [bağlanabilir](bindable.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**, **arabirim**, **birleşim**, **enum**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/win32/Midl/uuid)
