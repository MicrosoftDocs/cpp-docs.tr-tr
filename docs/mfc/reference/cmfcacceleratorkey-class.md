---
title: "CMFCAcceleratorKey sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
dev_langs: C++
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3303be9f37749436d140028cd5fa45cd4454c8c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey sınıfı
Sanal anahtar eşleme ve biçimlendirme uygulayan bir yardımcı sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Oluşturan bir `CMFCAcceleratorKey` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|Görsel gösterimi HIZLANDIRMA yapısına çevirir.|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|İçin kısayol tuşu ayarlar `CMFCAcceleratorKey` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hızlandırıcı tuşları kısayol tuşları da verilir. Bir kullanıcının girdiği, klavye kısayollarını görüntülemek istiyorsanız, [CMFCAcceleratorKeyAssignCtrl sınıfı](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) eşlemeleri klavye kısayolları, Alt + Shift + S gibi "Alt + üst karakter + S" gibi özel metin biçiminde. Her `CMFCAcceleratorKey` nesne bir metin biçimi tek kısayol tuşu eşler.  
  
 Kısayol tuşları ve Hızlandırıcı tabloları nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [CKeyboardManager sınıfı](../../mfc/reference/ckeyboardmanager-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCAcceleratorKey` nesne ve nasıl kullanılacağını kendi `Format` yöntemi.  
  
 [!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey"></a>CMFCAcceleratorKey::CMFCAcceleratorKey  
 Oluşturan bir [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesnesi.  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpAccel`  
 Bir kısayol tuşu gösteren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturduğunuzda, bir kısayol tuşu sağlamak için değil, bir `CMFCAccleratorKey`, kullanın [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) bir kısayol tuşu ile ilişkilendirilecek yöntemi, `CMFCAcceleratorKey` nesnesi.  
  
##  <a name="format"></a>CMFCAcceleratorKey::Format  
 HIZLANDIRMA yapısı ilişkili dize değerine dönüşür.  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`str`  
 Bir başvuru bir `CString` yöntemi çevrilmiş kısayol tuşunu nereye yazdığını nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, ilişkili kısayol tuşunu dize biçiminde alır. Dize biçimi ayarlayabileceğiniz bir [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) Oluşturucusu veya yöntemini kullanarak nesne [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).  
  
##  <a name="setaccelerator"></a>CMFCAcceleratorKey::SetAccelerator  
 İçin kısayol tuşu ayarlar [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) nesnesi.  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpAccel`  
 Bir kısayol tuşu gösteren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin kısayol tuşu ayarlamak için bu yöntemi kullanmak bir `CMFCAcceleratorKey` oluştururken, bir kısayol tuşu sağlamadıysanız `CMFCAcceleratorKey`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Sınıfı](../../mfc/reference/ckeyboardmanager-class.md)
