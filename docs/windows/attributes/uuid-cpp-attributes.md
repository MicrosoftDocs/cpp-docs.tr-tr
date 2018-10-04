---
title: uuid (C++ öznitelikleri) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2bd15720c30c3a3f298e0094304205fd7fe5caeb
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789866"
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
|**İçin geçerlidir**|**sınıf**, **yapı**, **arabirimi**, **birleşim**, **sabit listesi**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/desktop/Midl/uuid)  