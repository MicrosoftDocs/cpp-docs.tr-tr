---
description: 'Daha fazla bilgi edinin: CD2DMesh Class'
title: CD2DMesh sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: fbdb941d04b87df5c136f1925445564caab63443
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193376"
---
# <a name="cd2dmesh-class"></a>CD2DMesh sınıfı

ID2D1Mesh için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DMesh::CD2DMesh](#cd2dmesh)|Bir CD2DMesh nesnesi oluşturur.|
|[CD2DMesh:: ~ CD2DMesh](#_dtorcd2dmesh)|Yok edicisi. Bir D2D kafes nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DMesh:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DMesh:: Create](#create)|Bir CD2DMesh oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DMesh::D estroy](#destroy)|Bir CD2DMesh nesnesini yok eder. (Geçersiz kılmalar [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DMesh::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DMesh:: Get](#get)|ID2D1Mesh arabirimini döndürür|
|[CD2DMesh:: IsValid](#isvalid)|Kaynak geçerliliğini denetler (geçersiz kılmalar [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DMesh:: Open](#open)|Popülasyon için ağı açar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DMesh:: operator ID2D1Mesh *](#operator_id2d1mesh_star)|ID2D1Mesh arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DMesh:: m_pMesh](#m_pmesh)|Bir ID2D1Mesh işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dmeshcd2dmesh"></a><a name="_dtorcd2dmesh"></a> CD2DMesh:: ~ CD2DMesh

Yok edicisi. Bir D2D kafes nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DMesh();
```

## <a name="cd2dmeshattach"></a><a name="attach"></a> CD2DMesh:: Attach

Varolan kaynak arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

## <a name="cd2dmeshcd2dmesh"></a><a name="cd2dmesh"></a> CD2DMesh::CD2DMesh

Bir CD2DMesh nesnesi oluşturur.

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dmeshcreate"></a><a name="create"></a> CD2DMesh:: Create

Bir CD2DMesh oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dmeshdestroy"></a><a name="destroy"></a> CD2DMesh::D estroy

Bir CD2DMesh nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dmeshdetach"></a><a name="detach"></a> CD2DMesh::D etach

Nesneden kaynak arabirimini ayırır

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dmeshget"></a><a name="get"></a> CD2DMesh:: Get

ID2D1Mesh arabirimini döndürür

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Mesh arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dmeshisvalid"></a><a name="isvalid"></a> CD2DMesh:: IsValid

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse doğru; Aksi halde yanlış.

## <a name="cd2dmeshm_pmesh"></a><a name="m_pmesh"></a> CD2DMesh:: m_pMesh

Bir ID2D1Mesh işaretçisi.

```
ID2D1Mesh* m_pMesh;
```

## <a name="cd2dmeshopen"></a><a name="open"></a> CD2DMesh:: Open

Popülasyon için ağı açar.

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>Dönüş Değeri

Ağı doldurmak için kullanılan bir ID2D1TessellationSink işaretçisi.

## <a name="cd2dmeshoperator-id2d1mesh"></a><a name="operator_id2d1mesh_star"></a> CD2DMesh:: operator ID2D1Mesh *

ID2D1Mesh arabirimini döndürür

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Mesh arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
