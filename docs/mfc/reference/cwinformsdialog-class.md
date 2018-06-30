---
title: CWinFormsDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fe7c8518366065e93360187247cbd07df42d79f
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122503"
---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog sınıfı
Bir Windows Forms kullanıcı denetimi barındıran bir MFC iletişim kutusu sınıfı için sarmalayıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
    public CDialog  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TManagedControl`  
 MFC uygulamasında görüntülenecek .NET Framework kullanıcı denetimi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|Oluşturan bir `CWinFormsDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](#getcontrol)|Windows Forms kullanıcı denetimi için bir başvuru alır.|  
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Windows Forms kullanıcı denetimi için pencere tanıtıcı alır.|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|MFC iletişim kutusu oluşturarak ve üzerindeki bir Windows Forms kullanıcı denetimi barındırma başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|Değiştirir [CWinFormsDialog::GetControl](#getcontrol) ifadelerde.|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Bir Windows Forms kullanıcı denetimi için bir başvuru olarak bir tür çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CWinFormsDialog` MFC iletişim kutusu sınıfı için sarmalayıcı olduğu ( [CDialog](../../mfc/reference/cdialog-class.md)), bir Windows Forms kullanıcı denetimi barındıran. Bu, .NET Framework denetimleri kalıcı veya geçici bir MFC iletişim kutusunda görüntülenmesini sağlar.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md) ve [MFC iletişim kutusu olarak Windows formu kullanıcı denetimi barındırma](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h  
  
##  <a name="cwinformsdialog"></a>  CWinFormsDialog::CWinFormsDialog  
 Oluşturan bir `CWinFormsDialog` nesnesi.  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDTemplate*  
 Bir iletişim kutusu şablonu kaynak Kimliğini içerir. İletişim kutusu Düzenleyicisi iletişim şablonu oluşturmak ve uygulamanın kaynak betik dosyasında depolamak için kullanın. İletişim kutusu şablonları hakkında daha fazla bilgi için bkz: [CDialog sınıfı](../../mfc/reference/cdialog-class.md).  
  
##  <a name="getcontrol"></a>  CWinFormsDialog::GetControl  
 Windows Forms kullanıcı denetimi için bir başvuru alır.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 MFC iletişim kutusunda Windows Forms denetimini bir başvuru döndürür.  
  
##  <a name="getcontrolhandle"></a>  CWinFormsDialog::GetControlHandle  
 Windows Forms kullanıcı denetimi için pencere tanıtıcı alır.  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows Forms kullanıcı denetimi için pencere tanıtıcının döndürür.  
  
##  <a name="oninitdialog"></a>  CWinFormsDialog::OnInitDialog  
 MFC iletişim kutusu oluşturarak ve üzerindeki bir Windows Forms kullanıcı denetimi barındırma başlatır.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Uygulama giriş odağını denetimleri birine iletişim kutusunda ayarlanmış olup olmadığını belirten bir Boole değeri. Varsa `OnInitDialog` döndürür sıfır olmayan Windows ayarlar giriş odağını ilk denetime iletişim kutusunda. Bu yöntem, yalnızca uygulama açıkça giriş odağını denetimleri birine iletişim kutusunda ayarlamışsa 0 geri dönebilirsiniz.  
  
### <a name="remarks"></a>Açıklamalar  
 MFC iletişim kutusu oluşturulduğunda (kullanarak [oluşturma](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), veya [DoModal](../../mfc/reference/cdialog-class.md#domodal) yöntemi devralınan [CDialog](../../mfc/reference/cdialog-class.md)), bir WM_ INITDIALOG ileti gönderilir ve bu yöntem çağrılır. İletişim kutusu üzerinde bir Windows Forms denetimi örneği oluşturur ve kullanıcı denetimi için boyutuna uygun şekilde iletişim kutusunun boyutunu ayarlar. Ardından MFC iletişim kutusunda yeni denetim barındırır.  
  
 İletişim kutusu başlatıldığında özel işlem gerçekleştirmeniz gerekiyorsa, bu üye işlevi geçersiz kılar. Bu yöntemi kullanma hakkında daha fazla bilgi için bkz: [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).  
  
##  <a name="operator_-_gt"></a>  CWinFormsDialog::operator-&gt;  
 Değiştirir [CWinFormsDialog::GetControl](#getcontrol) ifadelerde.  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç değiştirir kullanışlı bir sözdizimi sağlar `GetControl` ifadelerde.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol_xor"></a>  CWinFormsDialog::operator TManagedControl ^  
 Bir Windows Forms kullanıcı denetimi için bir başvuru olarak bir tür çevirir.  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç türü bir Windows Forms denetimini bir başvuru olarak çevirir. İletmek için kullanılan bir `CWinFormsDialog<TManagedControl>` iletişim kutusu bir Windows Forms kullanıcı denetimi nesnesi için bir işaretçi kabul işlevlere.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md)   
 [CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
