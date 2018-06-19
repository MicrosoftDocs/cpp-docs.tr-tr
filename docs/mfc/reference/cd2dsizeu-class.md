---
title: CD2DSizeU sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa7c42216f55479050812b559f533829d55162b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349941"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU sınıfı
D2D1_SIZE_U için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CD2DSizeU : public D2D1_SIZE_U;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Fazla Yüklendi. Oluşturan bir `CD2DSizeU` nesnesini `D2D1_SIZE_U` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DSizeU::IsNull](#isnull)|Döndürür bir `boolean` bir ifade geçerli bir veri içerip içermediğini gösteren değeri ( `null`).|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CD2DSizeU::operator CSize](#operator_csize)|Dönüştürür `CD2DSizeU` için `CSize` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `D2D1_SIZE_U`  
  
 [CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrendertarget.h  
  
##  <a name="cd2dsizeu"></a>  CD2DSizeU::CD2DSizeU  
 CSize nesnesinden CD2DSizeU nesnesi oluşturur.  
  
```  
CD2DSizeU(const CSize& size);  
CD2DSizeU(const D2D1_SIZE_U& size);  
  CD2DSizeU(const D2D1_SIZE_U* size);

 
CD2DSizeU(
    UINT32 cx = 0,  
    UINT32 cy = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 Kaynak boyutu  
  
 `cx`  
 Kaynak genişliği  
  
 `cy`  
 Kaynak yüksekliği  
  
##  <a name="isnull"></a>  CD2DSizeU::IsNull  
 Bir ifade (boş) geçerli veri içerip içermediğini gösteren bir Boole değeri döndürür.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Genişlik ve yükseklik boş ise TRUE; Aksi takdirde FALSE.  
  
##  <a name="operator_csize"></a>  CD2DSizeU::operator CSize  
 CD2DSizeU CSize nesnesine dönüştürür.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 D2D boyutu geçerli değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
