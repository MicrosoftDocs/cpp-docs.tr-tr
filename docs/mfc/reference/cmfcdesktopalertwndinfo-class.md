---
title: CMFCDesktopAlertWndInfo sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b775b06f605edc68c6f1dbe47035d9ecf214b396
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo sınıfı
`CMFCDesktopAlertWndInfo` Sınıfı ile kullanılır [CMFCDesktopAlertWnd sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md). Masaüstü uyarı pencere açılırsa görüntülenen denetimleri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Görüntülenen simge için bir tanıtıcı.|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Masaüstü uyarı pencere üzerinde bir bağlantı ile ilişkili komut kimliği.|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Masaüstü uyarı penceresinde görüntülenen metin.|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Masaüstü uyarı penceresinde görüntülenen bağlantısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCDesktopAlertWndInfo` Sınıfı iletilir [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) yöntemi Masaüstü uyarı pencere varsayılan iletişim kutusunda görüntülenen öğeler belirtin. Varsayılan iletişim üç öğe içerebilir:  
  
-   Çağırarak ayarlanmış bir simge [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).  
  
-   Bir etiket veya çağırarak ayarlanır kısa mesaj [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).  
  
-   Çağırarak ayarlanmış bir bağlantı [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Bağlantı tıklatıldığında çalıştırılan komut ayarlamak için arama [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).  
  
 Varsayılan iletişim yeterli değilse, özel iletişim oluşturun ve ona geçirin [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) Bu sınıf kullanmak yerine yöntemi. Daha fazla bilgi için bkz: [CMFCDesktopAlertDialog sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli üyelerinde kullanımı gösterilmiştir `CMFCDesktopAlertWndInfo` sınıfı. Örneğin, tanıtıcı gösterilen simgeyi Masaüstü uyarı pencere, Masaüstü uyarı penceresinde görüntülenen bağlantı ve Masaüstü uyarı pencere üzerinde bir bağlantı ile ilişkili komut kimliği görüntülenen metni ayarlama gösterilmiştir. Bu örneğin parçasıdır [Masaüstü uyarı demosu örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxDesktopAlertDialog.h  
  
##  <a name="operator_eq"></a>  CMFCDesktopAlertWndInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `src`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_hicon"></a>  CMFCDesktopAlertWndInfo::m_hIcon  
 Görüntülenen simge için bir tanıtıcı.  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_nurlcmdid"></a>  CMFCDesktopAlertWndInfo::m_nURLCmdID  
 Masaüstü uyarı pencere üzerinde bir bağlantı ile ilişkili komut kimliği.  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı tarafından belirtilen bağlantıyı tıklattığında komut kimliği açılan pencerede sahibine gönderilen [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).  
  
##  <a name="m_strtext"></a>  CMFCDesktopAlertWndInfo::m_strText  
 Masaüstü uyarı penceresinde görüntülenen metin.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_strurl"></a>  CMFCDesktopAlertWndInfo::m_strURL  
 Masaüstü uyarı penceresinde görüntülenen bağlantısı.  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bağlantıyı tıklattığında, komut sahip [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) komut kimliği açılır pencere sahibine gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [CMFCDesktopAlertDialog Sınıfı](../../mfc/reference/cmfcdesktopalertdialog-class.md)
