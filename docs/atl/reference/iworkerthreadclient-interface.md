---
title: IWorkerThreadClient Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: 6a68f25f153a0ad2cf42ebfaa374ff63c5746fcd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326308"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient Sınıfı

`IWorkerThreadClient`[CWorkerThread](../../atl/reference/cworkerthread-class.md) sınıfının istemcileri tarafından uygulanan arabirimdir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
__interface IWorkerThreadClient
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Closehandle](#closehandle)|Bu nesneyle ilişkili tanıtıcıyı kapatmak için bu yöntemi uygulayın.|
|[Yürütmek](#execute)|Bu nesneyle ilişkili tanıtıcı sinyal olduğunda kodu yürütmek için bu yöntemi uygulayın.|

## <a name="remarks"></a>Açıklamalar

Sinyal verilen bir tanıtıcıya yanıt olarak bir alt iş parçacığı üzerinde yürütülmesi gereken bir kod varsa bu arabirimi uygulayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlutil.h

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorkerThreadClient::CloseHandle

Bu nesneyle ilişkili tanıtıcıyı kapatmak için bu yöntemi uygulayın.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>Parametreler

*hHandle*<br/>
Tutamacı kapatılmalı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada bir hata HRESULT'ı döndürün.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tutamaç daha önce CWorkerThread bir çağrı ile bu nesne ile [ilişkili::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Örnek

Aşağıdaki kod basit bir `IWorkerThreadClient::CloseHandle`uygulama gösterir.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a>IWorkerThreadClient::Çalıştır

Bu nesneyle ilişkili tanıtıcı sinyal olduğunda kodu yürütmek için bu yöntemi uygulayın.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Parametreler

*dwParam*<br/>
Kullanıcı parametresi.

*hObject*<br/>
Sinyal verilen kulp.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada bir hata HRESULT'ı döndürün.

### <a name="remarks"></a>Açıklamalar

Bu yönteme geçirilen tutamaç ve DWORD/işaretçisi daha önce Bu nesneyle [CWorkerThread:AddHandle'a](../../atl/reference/cworkerthread-class.md#addhandle)yapılan bir çağrıyla ilişkilendirildi.

### <a name="example"></a>Örnek

Aşağıdaki kod basit bir `IWorkerThreadClient::Execute`uygulama gösterir.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread Sınıfı](../../atl/reference/cworkerthread-class.md)
