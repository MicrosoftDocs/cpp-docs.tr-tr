---
description: ': IWorkerThreadClient arabirimi hakkında daha fazla bilgi edinin'
title: IWorkerThreadClient arabirimi
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: fb9113c9380453dad9f647fa2f5a2095ff12cea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157990"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient arabirimi

`IWorkerThreadClient` , [CWorkerThread](../../atl/reference/cworkerthread-class.md) sınıfının istemcileri tarafından uygulanan arabirimdir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
__interface IWorkerThreadClient
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[CloseHandle](#closehandle)|Bu nesneyle ilişkili tanıtıcıyı kapatmak için bu yöntemi uygulayın.|
|[Yürütme](#execute)|Bu nesneyle ilişkili tanıtıcı sinyal geldiğinde kodu yürütmek için bu yöntemi uygulayın.|

## <a name="remarks"></a>Açıklamalar

Bir tanıtıcıya yanıt olarak bir çalışan iş parçacığında yürütülmesi gereken kodunuz olduğunda bu arabirimi uygulayın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlutil. h

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a> IWorkerThreadClient:: CloseHandle

Bu nesneyle ilişkili tanıtıcıyı kapatmak için bu yöntemi uygulayın.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>Parametreler

*hHandle*<br/>
Kapatılacak tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tanıtıcı daha önce bu nesneyle bir [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)çağrısıyla ilişkilendirildi.

### <a name="example"></a>Örnek

Aşağıdaki kod, ' nin basit bir uygulamasını gösterir `IWorkerThreadClient::CloseHandle` .

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a> IWorkerThreadClient:: Execute

Bu nesneyle ilişkili tanıtıcı sinyal geldiğinde kodu yürütmek için bu yöntemi uygulayın.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parametreler

*dwParam*<br/>
Kullanıcı parametresi.

*hObject*<br/>
Sinyali verilmiş olan tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tanıtıcı ve DWORD/işaretçi, daha önce bu nesneyle bir [CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)çağrısıyla ilişkilendirildi.

### <a name="example"></a>Örnek

Aşağıdaki kod, ' nin basit bir uygulamasını gösterir `IWorkerThreadClient::Execute` .

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread sınıfı](../../atl/reference/cworkerthread-class.md)
