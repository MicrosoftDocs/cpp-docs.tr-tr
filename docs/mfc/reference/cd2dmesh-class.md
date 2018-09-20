---
title: CD2DMesh sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
dev_langs:
- C++
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7ed748a7f098dcbec68decbff29f8973e0b8476
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405989"
---
# <a name="cd2dmesh-class"></a>CD2DMesh sınıfı

ID2D1Mesh için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DMesh::CD2DMesh](#cd2dmesh)|CD2DMesh bir nesne oluşturur.|
|[CD2DMesh:: ~ CD2DMesh](#_dtorcd2dmesh)|Yıkıcı. D2D kafes nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DMesh::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DMesh::Create](#create)|Bir CD2DMesh oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DMesh::Destroy](#destroy)|CD2DMesh nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DMesh::detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DMesh::get](#get)|Döndürür ID2D1Mesh arabirimi|
|[CD2DMesh::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DMesh::Open](#open)|Kafes nüfusunu açılır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DMesh::operator ID2D1Mesh *](#operator_id2d1mesh_star)|Döndürür ID2D1Mesh arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DMesh::m_pMesh](#m_pmesh)|Bir ID2D1Mesh işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dmesh"></a>  CD2DMesh:: ~ CD2DMesh

Yıkıcı. D2D kafes nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DMesh();
```

##  <a name="attach"></a>  CD2DMesh::Attach

Var olan kaynak arabirimi nesnesine ekler

```
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

##  <a name="cd2dmesh"></a>  CD2DMesh::CD2DMesh

CD2DMesh bir nesne oluşturur.

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi için bir işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="create"></a>  CD2DMesh::Create

Bir CD2DMesh oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DMesh::Destroy

CD2DMesh nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DMesh::detach

Kaynak arabirimi nesnesinden ayırır

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="get"></a>  CD2DMesh::get

Döndürür ID2D1Mesh arabirimi

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Mesh arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="isvalid"></a>  CD2DMesh::IsValid

Kaynak geçerlilik denetimleri

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_pmesh"></a>  CD2DMesh::m_pMesh

Bir ID2D1Mesh işaretçisi.

```
ID2D1Mesh* m_pMesh;
```

##  <a name="open"></a>  CD2DMesh::Open

Kafes nüfusunu açılır.

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>Dönüş Değeri

Kafes doldurmak için kullanılan bir ID2D1TessellationSink işaretçisi.

##  <a name="operator_id2d1mesh_star"></a>  CD2DMesh::operator ID2D1Mesh *

Döndürür ID2D1Mesh arabirimi

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Mesh arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
