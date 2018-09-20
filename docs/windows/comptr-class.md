---
title: ComPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr class
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88d3af154993bea6df509a69b832223aede7ad81
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386515"
---
# <a name="comptr-class"></a>ComPtr Sınıfı

Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirlenen arabirimi temsil eden tür. **ComPtr** otomatik olarak temel arabirim işaretçisi için bir başvuru sayısını tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Arabirimi, **ComPtr** temsil eder.

*U*<br/>
Bir sınıfa geçerli **ComPtr** arkadaş olur. (Bu parametre kullanan bir şablonu korunuyor.)

## <a name="remarks"></a>Açıklamalar

`ComPtr<>` temel arabirim işaretçisi temsil eden bir tür bildirir. Kullanma `ComPtr<>` bir değişkeni bildirir ve ardından OK üye erişimi işleci (`->`) bir arabirim üye işlevine erişmek için.

Akıllı işaretçiler hakkında daha fazla bilgi için bkz: "COM akıllı işaretçileri" alt bölümü [COM kodlama uygulamalarını](/windows/desktop/LearnWin32/com-coding-practices)MSDN Kitaplığı'nda konu.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`InterfaceType`|Tarafından belirtilen türe ilişkin bir eşanlam *T* şablon parametresi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[ComPtr::ComPtr Oluşturucusu](../windows/comptr-comptr-constructor.md)|Yeni bir örneğini başlatır **ComPtr** sınıfı. Varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları aşırı yüklemeler sağlar.|
|[ComPtr::~ComPtr Yıkıcısı](../windows/comptr-tilde-comptr-destructor.md)|Örneği başlatılmasını geri alır **ComPtr**.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ComPtr::As Metodu](../windows/comptr-as-method.md)|Döndürür bir **ComPtr** belirtilen şablon parametresi tarafından belirlenen arabirimi temsil eden nesne.|
|[ComPtr::AsIID Metodu](../windows/comptr-asiid-method.md)|Döndürür bir **ComPtr** belirtilen arabirim kimliği. tarafından belirlenen arabirimi temsil eden nesne|
|[ComPtr::AsWeak Metodu](../windows/comptr-asweak-method.md)|Geçerli nesnenin zayıf bir başvuru alır.|
|[ComPtr::Attach Metodu](../windows/comptr-attach-method.md)|Bu ilişkilendirir **ComPtr** geçerli bir şablon türü parametresi tarafından belirtilen arabirim türüne sahip.|
|[ComPtr::CopyTo Metodu](../windows/comptr-copyto-method.md)|Şununla ilişkili geçerli ya da belirtilen arabirim kopyalar **ComPtr** belirtilen çıkış işaretçi.|
|[ComPtr::Detach Metodu](../windows/comptr-detach-method.md)|Bu ayırır **ComPtr** arabiriminden temsil eder.|
|[ComPtr::Get Metodu](../windows/comptr-get-method.md)|Şununla ilişkili arabirim işaretçisi alır **ComPtr**.|
|[ComPtr::GetAddressOf Metodu](../windows/comptr-getaddressof-method.md)|Adresini alır [ptr_](../windows/comptr-ptr-data-member.md) bu tarafından temsil edilen arabirimi için bir işaretçi içeren veri üyesi **ComPtr**.|
|[ComPtr::ReleaseAndGetAddressOf Metodu](../windows/comptr-releaseandgetaddressof-method.md)|Şununla ilişkili arabirimini yayımlar **ComPtr** ve adresini alır. [ptr_](../windows/comptr-ptr-data-member.md) yayımlanan arabirimi için bir işaretçi içeren veri üyesi.|
|[ComPtr::Reset](../windows/comptr-reset.md)|Bununla ilişkili arabirim işaretçisi için tüm başvurularını serbest **ComPtr**.|
|[ComPtr::Swap Metodu](../windows/comptr-swap-method.md)|Geçerli tarafından yönetilen arabirimi birbiriyle değiştirir **ComPtr** tarafından belirtilen yönetilen arabirimi ile **ComPtr**.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ComPtr::InternalAddRef Metodu](../windows/comptr-internaladdref-method.md)|Şununla ilişkili arabiriminin başvuru sayısını artırır **ComPtr**.|
|[ComPtr::InternalRelease Metodu](../windows/comptr-internalrelease-method.md)|Şununla ilişkili arabirim bir COM yayınında işlemi gerçekleştirir **ComPtr**.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[ComPtr::operator Microsoft::WRL::Details::BoolType İşleci](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|Belirtir olup olmadığını bir **ComPtr** bir arabirimin nesne ömrü yönetimi.|
|[ComPtr::operator& İşleci](../windows/comptr-operator-ampersand-operator.md)|Geçerli adresi alır **ComPtr**.|
|[ComPtr::operator= İşleci](../windows/comptr-operator-assign-operator.md)|Geçerli bir değer atar **ComPtr**.|
|[ComPtr::operator-> İşleci](../windows/comptr-operator-arrow-operator.md)|Geçerli bir şablon parametresi tarafından belirtilen tür için bir işaretçi alır.|
|[ComPtr::operator== İşleci](../windows/comptr-operator-equality-operator.md)|Belirtir olup iki **ComPtr** nesneler.|
|[ComPtr::operator!= İşleci](../windows/comptr-operator-inequality-operator.md)|Belirtir olup iki **ComPtr** nesneler eşit değildir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[ComPtr::ptr_ Veri Üyesi](../windows/comptr-ptr-data-member.md)|İle ilişkili olan ve bu tarafından yönetilen arabirimi için bir işaretçi içeren **ComPtr**.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)