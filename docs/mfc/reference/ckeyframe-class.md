---
title: CKeyFrame sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
dev_langs:
- C++
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56fa354a46e40704ac063791931ca01d1386a558
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038464"
---
# <a name="ckeyframe-class"></a>CKeyFrame sınıfı
Animasyon ana kare temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|Fazla Yüklendi. Diğer ana kare üzerinde bağlı bir ana kare oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Bir ana kare bir film şeridi ekler. (Geçersiz kılmaları [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Geçişten sonra film şeridi için ana kare ekler.|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Bir ana kare uzaklıkta film şeridi ekler.|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Bu ana kare bağımlı bir anahtar kareye bir işaretçi döndürür.|  
|[CKeyFrame::GetOffset](#getoffset)|Diğer ana kare bir uzaklığını döndürür.|  
|[CKeyFrame::GetTransition](#gettransition)|Bu ana kare bağımlı bir geçiş için bir işaretçi döndürür.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|Bu ana kare m_pExistingKeyFrame içinde depolanan bir ana kare gelen uzaklığını belirtir.|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Bir işaretçi var olan bir keframe depolar. Bu ana kare varolan anahtar kareye m_offset ile film şeridi eklenir.|  
|[CKeyFrame::m_pTransition](#m_ptransition)|Bu ana kare başlayan transtion gösteren bir işaretçi depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf bir animasyon ana kare uygular. Bir ana kare film şeridi sürede birazdan temsil eder ve geçişleri başlangıç ve bitiş zamanları belirtmek için kullanılır. Bir ana kare diğer ana kare üzerinde temel olabilir ve uzaklık (saniye cinsinden), sahip veya bir geçiş üzerinde temel olabilir ve bu geçiş sona erdiğinde zaman birazdan temsil eder.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard  
 Bir ana kare bir film şeridi ekler.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStoryboard*  
 Film şeridi gösteren bir işaretçi.  
  
 *bDeepAdd*  
 Ana kare ekleyin veya yinelemeli olarak geçiş belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE, ana kare başarıyla eklendi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir ana kare film şeridi ekler. Diğer ana kare veya geçiş bağlıdır ve bDeepAdd TRUE ise, yinelemeli olarak eklemek bu yöntem çalışır.  
  
##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition  
 Geçişten sonra film şeridi için ana kare ekler.  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStoryboard*  
 Film şeridi gösteren bir işaretçi.  
  
 *bDeepAdd*  
 Bir geçiş yinelemeli olarak eklenip eklenmeyeceğini belirler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE, ana kare başarıyla eklendi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, geçişten sonra film şeridi için ana kare eklemek için çerçevesi tarafından çağrılır.  
  
##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset  
 Bir ana kare uzaklıkta film şeridi ekler.  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStoryboard*  
 Film şeridi gösteren bir işaretçi.  
  
 *bDeepAdd*  
 Bir ana kare eklemek için bu ana kare üzerinde yinelemeli olarak bağlı olup olmadığını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE, ana kare başarıyla eklendi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bir ana kare uzaklıkta film şeridi eklemek için framework tarafından çağrılır.  
  
##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame  
 Bir geçiş üzerinde bağlıdır bir ana kare oluşturur.  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Parametreler  
 *pTransition*  
 Bir geçiş için bir işaretçi.  
  
 *pKeyframe*  
 Ana kare bir işaretçi.  
  
 *uzaklık*  
 PKeyframe tarafından belirtilen ana kare gelen saniye cinsinden uzaklık.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen geçiş sona erdiğinde oluşturulan ana kareyi film şeridi sürede birazdan temsil eder.  
  
##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe  
 Bu ana kare bağımlı bir anahtar kareye bir işaretçi döndürür.  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi ana kare ya da bu ana kare diğer ana kare üzerinde bağlı değildir yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ana kare bağımlı bir anahtar kareye erişimci budur.  
  
##  <a name="getoffset"></a>  CKeyFrame::GetOffset  
 Diğer ana kare bir uzaklığını döndürür.  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Diğer ana kare gelen saniye cinsinden uzaklık.  
  
### <a name="remarks"></a>Açıklamalar  
 Diğer ana kare gelen saniye cinsinden uzaklık belirlemek için bu yöntem çağrılmalıdır.  
  
##  <a name="gettransition"></a>  CKeyFrame::GetTransition  
 Bu ana kare bağımlı bir geçiş için bir işaretçi döndürür.  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi geçiş ya da bu ana kare geçişi bağlı değildir yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ana kare bağımlı bir geçiş için bir erişimci budur.  
  
##  <a name="m_offset"></a>  CKeyFrame::m_offset  
 Bu ana kare m_pExistingKeyFrame içinde depolanan bir ana kare gelen uzaklığını belirtir.  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame  
 Bir işaretçi var olan bir keframe depolar. Bu ana kare varolan anahtar kareye m_offset ile film şeridi eklenir.  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="m_ptransition"></a>  CKeyFrame::m_pTransition  
 Bu ana kare başlayan transtion gösteren bir işaretçi depolar.  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
