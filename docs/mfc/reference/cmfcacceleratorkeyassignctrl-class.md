---
title: CMFCAcceleratorKeyAssignCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a2906071ce1e8c8f65f21554915feed0d134276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl sınıfı
`CMFCAcceleratorKeyAssignCtrl` Sınıfını genişleten [CEdit sınıfı](../../mfc/reference/cedit-class.md) ALT, Denetim ve kaydırma gibi ek sistem düğmeleri desteklemek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCAcceleratorKeyAssignCtrl : public CEdit  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|Oluşturan bir `CMFCAcceleratorKeyAssignCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|Alır `ACCEL` bir kısayol tuşuna basılı için yapı `CMFCAcceleratorKeyAssignCtrl` nesnesi.|  
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||  
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|Bir kısayol tuşu tanımlı olup olmadığını belirler.|  
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|Sınıfı tarafından kullanılan [CWinApp](../../mfc/reference/cwinapp-class.md) için gönderilen önce pencere iletileri çevirmek için [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|Kısayol tuşu sıfırlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf işlevselliğini genişleten `CEdit` kısayol tuşları, olarak da bilinen Hızlandırıcı tuşları destekleme tarafından sınıfı. `CMFCAcceleratorKeyAssignCtrl` Sınıf olarak işlev bir [CEdit sınıfı](../../mfc/reference/cedit-class.md) ve sistem düğmeleri tanıyabilirsiniz.  
  
 Bu sınıf fiziksel kısayol tuş birleşimleri dize değerine eşler. Örneğin, ALT anahtar birleşimi varsayın + B "Alt + B" dizeye eşlendi. Kullanıcı, bu tuş bileşimini bastığında bir `CMFCAcceleratorKeyAssignCtrl` nesnesi, "Alt + B", kullanıcıya görüntülenir. Kısayol tuşları ve dize biçimi arasında eşleme hakkında daha fazla bilgi için bkz: [CMFCAcceleratorKey sınıfı](../../mfc/reference/cmfcacceleratorkey-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCAcceleratorKeyAssignCtrl` nesne ve kullanmak kendi `ResetKey` kısayol tuşu sıfırlama yöntemi.  
  
 [!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CMFCAcceleratorKeyAssignCtrl`   
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxacceleratorkeyassignctrl.h  
  
##  <a name="cmfcacceleratorkeyassignctrl"></a>  CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl  
 Oluşturan bir [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesi.  
  
```  
CMFCAcceleratorKeyAssignCtrl();
```  
  
##  <a name="getaccel"></a>  CMFCAcceleratorKeyAssignCtrl::GetAccel  
 Alır `ACCEL` bir kısayol tuşuna basılı için yapı [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesi.  
  
```  
ACCEL const* GetAccel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `ACCEL` kısayol tuşu açıklar yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Almak için bu işlevi kullanın `ACCEL` kullanıcı girilen bir kısayol tuşu için yapısı, `CMFCAcceleratorKeyAssignCtrl` nesnesi.  
  
##  <a name="isfocused"></a>  CMFCAcceleratorKeyAssignCtrl::IsFocused  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsFocused() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="iskeydefined"></a>  CMFCAcceleratorKeyAssignCtrl::IsKeyDefined  
 Bir kısayol tuşu içinde tanımlanmış olup olmadığını belirler [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) nesnesi.  
  
```  
BOOL IsKeyDefined() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı zaten bir kısayol tuşu tanımlamak anahtarları geçerli bir birleşimi basıldıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir geçerli kısayol tuşu girilen olup olmadığını belirlemek için bu işlevi kullanın, `CMFCAcceleratorKeyAssignCtrl` nesnesi. Bir kısayol tuşu varsa, kullanabileceğiniz [CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel) elde etmek için yöntemi `ACCEL` bu kısayol anahtar ile ilişkili yapısı.  
  
##  <a name="pretranslatemessage"></a>  CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pMsg`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="resetkey"></a>  CMFCAcceleratorKeyAssignCtrl::ResetKey  
 Kısayol tuşu sıfırlar.  
  
```  
void ResetKey();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev Düzenle denetim metni temizler. Bu kullanıcı basılı herhangi bir kısayol tuşları içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCAcceleratorKey Sınıfı](../../mfc/reference/cmfcacceleratorkey-class.md)
