---
title: uuid (C++ Öznitelikleri)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: 8d9d55fc2a340165480cab4036ad1e5323e6b625
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026048"
---
# <a name="uuid-c-attributes"></a>uuid (C++ Öznitelikleri)

Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ uuid(
   "uuid"
) ]
```

### <a name="parameters"></a>Parametreler

*uuid*<br/>
128-bit, benzersiz tanımlayıcısı.

## <a name="remarks"></a>Açıklamalar

Bir arabirim veya sınıf tanımını belirtme **UUID** C++ özniteliği ve ardından Visual C++ derleyicisi sağlar; biri. Belirttiğinizde bir **UUID**, tırnak işaretleri eklemeniz gerekir.

Siz belirtmezseniz **UUID**, derleyici bir makinede farklı öznitelik projelerinde arabirimler veya aynı ada sahip sınıflar için aynı GUID oluşturur.

Uuidgen.exe veya Guidgen.exe kendi benzersiz kimlikler oluşturmak için kullanabilirsiniz. (Bu araçlardan birini çalıştırmak için tıklayın **Başlat** tıklatıp **çalıştırma** menüsünde. Ardından gerekli aracının adını girin.)

ATL ayrıca kullanmayan bir projede kullanılan belirttiğinizde **UUID** özniteliktir belirtmekle aynı [UUID](../../cpp/uuid-cpp.md) **__declspec** değiştiricisi. Alınacak **UUID** bir sınıfı, kullandığınız [__uuidof](../../cpp/uuidof-operator.md)

## <a name="example"></a>Örnek

Bkz: [bağlanabilir](bindable.md) örnek kullanımını örneğin **UUID**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**sınıf**, **yapı**, **arabirimi**, **birleşim**, **sabit listesi**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/desktop/Midl/uuid)