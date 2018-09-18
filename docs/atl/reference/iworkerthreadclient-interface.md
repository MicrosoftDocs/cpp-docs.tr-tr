---
title: Iworkerthreadclient | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c0261964f2e9c33f8a594a83e1b19c1db7be614
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069241"
---
# <a name="iworkerthreadclient-interface"></a>Iworkerthreadclient sınıfı

`IWorkerThreadClient` istemcileri tarafından uygulanan arabirimi [CWorkerThread](../../atl/reference/cworkerthread-class.md) sınıfı.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
__interface IWorkerThreadClient
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CloseHandle](#closehandle)|Bu nesneyle ilişkili tanıtıcı kapatmak için bu yöntemi uygular.|
|[Execute](#execute)|Bu nesneyle ilişkili tanıtıcı sinyal olur olduğunda kod yürütmek için bu yöntemi uygular.|

## <a name="remarks"></a>Açıklamalar

Yanıt sinyalliye dönüşmesi bir tanıtıcı bir çalışan iş parçacığında yürütmek için gereken kodu varsa, bu arabirimi uygulayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle

Bu nesneyle ilişkili tanıtıcı kapatmak için bu yöntemi uygular.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>Parametreler

*hHandle*<br/>
Kapatılması tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı veya başarısızlık durumunda bir hata HRESULT S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tanıtıcı bir çağrı tarafından bu nesne ile daha önce ilişkili [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Örnek

Aşağıdaki kod basit bir uygulamasını gösterir `IWorkerThreadClient::CloseHandle`.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

##  <a name="execute"></a>  IWorkerThreadClient::Execute

Bu nesneyle ilişkili tanıtıcı sinyal olur olduğunda kod yürütmek için bu yöntemi uygular.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parametreler

*dwParam*<br/>
Kullanıcı parametresi.

*hObject*<br/>
Sinyal haline tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarı veya başarısızlık durumunda bir hata HRESULT S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı ve DWORD/işaretçi bu yönteme bir çağrı tarafından bu nesne ile daha önce ilişkili [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Örnek

Aşağıdaki kod basit bir uygulamasını gösterir `IWorkerThreadClient::Execute`.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread Sınıfı](../../atl/reference/cworkerthread-class.md)
