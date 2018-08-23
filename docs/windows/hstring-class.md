---
title: HString sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
dev_langs:
- C++
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eea40f989e7d41afbff2773fcc5e6e5b2cfbafd2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613659"
---
# <a name="hstring-class"></a>HString Sınıfı

Bir HSTRING RAII deseni kullanılarak ömrünü yönetmek için yardımcı sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
class HString;
```

## <a name="remarks"></a>Açıklamalar

Windows çalışma zamanı HSTRING tutamaçları ile dizelere erişim sağlar. **Hstrıng** kullanışlı işlevler ve işleçler HSTRING tutamaçları kullanmayı kolaylaştırmak için sınıf sağlar. Bu sınıf, bir RAII deseni sahip HSTRING ömrü başa çıkabilir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[HString::HString Oluşturucusu](../windows/hstring-hstring-constructor.md)|Yeni bir örneğini başlatır **Hstrıng** sınıfı.|
|[HString::~HString Yıkıcısı](../windows/hstring-tilde-hstring-destructor.md)|Geçerli örneğini yok eder **Hstrıng** sınıfı.|

### <a name="members"></a>Üyeler

|Ad|Açıklama|
|----------|-----------------|
|[HString::Set Metodu](../windows/hstring-set-method.md)|Geçerli değerini ayarlar **Hstrıng** belirtilen geniş karakter dizesini bir nesneye veya **Hstrıng** parametresi.|
|[HString::Attach Metodu](../windows/hstring-attach-method.md)|Belirtilen ilişkilendirir **Hstrıng** geçerli nesneyle **Hstrıng** nesne.|
|[HString::CopyTo Metodu](../windows/hstring-copyto-method.md)|Geçerli kopyalar **Hstrıng** nesnesini bir HSTRING nesnesine.|
|[HString::Detach Metodu](../windows/hstring-detach-method.md)|Belirtilen ayırır **Hstrıng** nesnesini temel değerinden.|
|[HString::GetAddressOf Metodu](../windows/hstring-getaddressof-method.md)|Temel HSTRING tanıtıcısına bir işaretçi alır.|
|[HString::Get Metodu](../windows/hstring-get-method.md)|Temel HSTRING tanıtıcısının değerini alır.|
|[HString::Release Metodu](../windows/hstring-release-method.md)|Temel dize değerini siler ve geçerli başlatır **Hstrıng** boş bir değere nesne.|
|[HString::MakeReference Metodu](../windows/hstring-makereference-method.md)|Oluşturur bir `HStringReference` nesnesinden belirtilen dize parametresi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HString::Operator= İşleci](../windows/hstring-operator-assign-operator.md)|Başka bir değer taşır **Hstrıng** geçerli nesneye **Hstrıng** nesne.|
|[HString::Operator== İşleci](../windows/hstring-operator-equality-operator.md)|İki parametrenin eşit olup olmadığını gösterir.|
|[HString::Operator!= İşleci](../windows/hstring-operator-inequality-operator.md)|İki parametrenin eşit olup olmadığını gösterir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HString`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)