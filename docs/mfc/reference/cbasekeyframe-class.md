---
title: CBaseKeyFrame sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
dev_langs:
- C++
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3de348131dded63794e818d40c0ac5aeae910b03
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956715"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame sınıfı
Bir ana kare temel işlevlerini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Bir ana kare nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|Bir ana kare film şeridi ekler.|  
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Temel alınan ana kare değeri döndürür.|  
|[CBaseKeyFrame::IsAdded](#isadded)|Bir ana kare film şeridi eklenmiş olup olmadığını bildirir.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Ana kareyi uzaklığındaki veya geçiş sonrasında film şeridi için eklenmesi gerekip gerekmediğini belirtir.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBaseKeyFrame::m_bAdded](#m_badded)|Bu ana kare bir film şeridi eklenmiş olup olmadığını belirtir.|  
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Bu ana kare başka bir var olan ana kare uzaklık veya bazı geçiş işleminin sonunda film şeridi için eklenmesi gerekip gerekmediğini belirtir.|  
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Bir Windows animasyon API ana kare temsil eder. Bir ana kare başlatılmadı, önceden tanımlanmış değer UI_ANIMATION_KEYFRAME_STORYBOARD_START ayarlanır.|  
  
## <a name="remarks"></a>Açıklamalar  
 UI_ANIMATION_KEYFRAME değişkeni yalıtır. Herhangi bir ana kare uygulaması için bir taban sınıf görevi görür. Bir ana kare film şeridi sürede birazdan temsil eder ve geçişleri başlangıç ve bitiş zamanları belirtmek için kullanılır. Ana kare - ana kare belirtilen uzaklığından (saat) film şeridi eklendi veya belirtilen geçişten sonra eklenen ana kareler iki tür vardır. Bazı geçişler sürelerini animasyon başlamadan önce bilinen yapılamıyor çünkü bazı ana kare gerçek değerler yalnızca çalışma zamanında belirlenir. Ana kare ana kare üzerinde bağlı, olan ve dolayısıyla geçişleri üzerinde bağımlı olduğu için ana kare zincirleri oluştururken sonsuz özyinelemelerin önlemek önemlidir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseKeyFrame`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>  CBaseKeyFrame::AddToStoryboard  
 Bir ana kare film şeridi ekler.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStoryboard*  
 Film şeridi gösteren bir işaretçi.  
  
 *bDeepAdd*  
 Bu parametre TRUE olur ve diğer bazı ana kare veya geçiş eklenmekte olan ana kareyi bağlıdır, bu yöntem bu kare veya ilk film şeridi için geçiş eklemeye çalışır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ana kare başarıyla film şeridi eklenmişse TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir ana kare film şeridi eklemek için çağrılır.  
  
##  <a name="cbasekeyframe"></a>  CBaseKeyFrame::CBaseKeyFrame  
 Bir ana kare nesnesi oluşturur.  
  
```  
CBaseKeyFrame();
```  
  
##  <a name="getanimationkeyframe"></a>  CBaseKeyFrame::GetAnimationKeyframe  
 Temel alınan ana kare değeri döndürür.  
  
```  
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir ana kare. UI_ANIMATION_KEYFRAME_STORYBOARD_START varsayılan değerdir.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel alınan ana kare değeri için bir erişimci budur.  
  
##  <a name="isadded"></a>  CBaseKeyFrame::IsAdded  
 Bir ana kare film şeridi eklenmiş olup olmadığını bildirir.  
  
```  
BOOL IsAdded() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir ana kare bir film şeridi eklenirse TRUE; otehrwise FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban sınıf içinde IsAdded her zaman TRUE değerini döndürür, ancak türetilmiş sınıflarda geçersiz kılındı.  
  
##  <a name="iskeyframeatoffset"></a>  CBaseKeyFrame::IsKeyframeAtOffset  
 Ana kareyi uzaklığındaki veya geçiş sonrasında film şeridi için eklenmesi gerekip gerekmediğini belirtir.  
  
```  
BOOL IsKeyframeAtOffset() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ana kareyi bazı belirtilen uzaklıkta film şeridi eklenecekse TRUE. Ana kareyi bazı geçişten sonra film şeridi eklenecekse FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Ana kareyi uzaklıkta film şeridi için eklenmesi gerekip gerekmediğini belirtir. Uzaklık ya da geçiş türetilen bir sınıfta belirtilmelidir.  
  
##  <a name="m_badded"></a>  CBaseKeyFrame::m_bAdded  
 Bu ana kare bir film şeridi eklenmiş olup olmadığını belirtir.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_biskeyframeatoffset"></a>  CBaseKeyFrame::m_bIsKeyframeAtOffset  
 Bu ana kare başka bir var olan ana kare uzaklık veya bazı geçiş işleminin sonunda film şeridi için eklenmesi gerekip gerekmediğini belirtir.  
  
```  
BOOL m_bIsKeyframeAtOffset;  
```  
  
##  <a name="m_keyframe"></a>  CBaseKeyFrame::m_keyframe  
 Bir Windows animasyon API ana kare temsil eder. Bir ana kare başlatılmadı, önceden tanımlanmış değer UI_ANIMATION_KEYFRAME_STORYBOARD_START ayarlanır.  
  
```  
UI_ANIMATION_KEYFRAME m_keyframe;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
