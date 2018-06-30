---
title: Ddx_managedcontrol sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00ec945c5f0cdbb0c12f49b90719c31bf841ef2f
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121643"
---
# <a name="cwinformscontrol-class"></a>Ddx_managedcontrol sınıfı
Bir Windows Forms denetimini barındırmak için temel işlevleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TManagedControl`  
 MFC uygulamada görüntülenecek bir .NET Framework Windows Forms denetimi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Bir MFC Windows Forms denetimi sarmalayıcı nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Windows Forms denetimini bir MFC kapsayıcıda oluşturur.|  
|[CWinFormsControl::GetControl](#getcontrol)|Windows Forms denetimi için bir işaretçi alır.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Windows Forms denetimi için bir tanıtıcı alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Değiştirir [CWinFormsControl::GetControl](#getcontrol) ifadelerde.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Bir Windows Forms denetimi için bir işaretçi olarak bir tür çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CWinFormsControl` Sınıfı bir Windows Forms denetimi barındırma için temel işlevselliği sağlar.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 MFC kodunuzu pencere işleyicileri önbelleğe kaydetmelisiniz (genellikle depolanan `m_hWnd`). Bazı Windows Forms Denetim Özellikleri gerektiren temel Win32 `Window` yok edilmesi ve kullanılarak yeniden `DestroyWindow` ve `CreateWindow`. MFC Windows Forms uygulaması işler `Destroy` ve `Create` güncelleştirmek için denetim olayları `m_hWnd` üyesi.  
  
> [!NOTE]
>  MFC Windows Forms tümleştirme yalnızca dinamik olarak (AFXDLL tanımlandığı) ile MFC'ye projeleri çalışır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h  
  
##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl  
 Windows Forms denetimini bir MFC kapsayıcıda oluşturur.  
  
```  
inline BOOL CreateManagedControl(
    System::Type^ pType,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID)  
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);

 
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    int nPlaceHolderID,  
    CWnd* pParentWnd);

 
inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *pType*  
 Oluşturulacak denetim veri türü. Olmalıdır bir [türü](https://msdn.microsoft.com/en-us/library/system.type) veri türü.  
  
 *dwStyle*  
 Denetime uygulamak için pencere stili. Bir birleşimini belirtin [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles). Şu anda yalnızca aşağıdaki stillerini desteklenir: WS_TABSTOP, ws_vısıble, ws_dısabled ve WS_GROUP.  
  
 *Rect*  
 A [RECT yapısı](../../mfc/reference/rect-structure1.md) denetiminin sol üst ve sağ alt köşe koordinatlarını tanımlar (ilk aşırı yükleme yalnızca).  
  
 *nPlaceHolderID*  
 Statik yer tutucu denetiminin tanıtıcısı kaynak düzenleyicisinde yerleştirilir. Yeni oluşturulan Windows Forms denetimi konum, z düzenini ve stili varsayılarak statik denetimi değiştirir (ikinci aşırı yükleme yalnızca).  
  
 *pParentWnd*  
 Üst pencere için bir işaretçi.  
  
 *nID*  
 Yeni oluşturulan denetimine atanan kaynak kimlik numarası.  
  
 *pControl*  
 Bir Windows Forms denetimi ile ilişkilendirilecek örneği [Ddx_managedcontrol](../../mfc/reference/cwinformscontrol-class.md) nesne (yalnızca dördüncü aşırı).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, sıfır olmayan bir değer döndürür. İşlem başarısız olursa, sıfır döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem .NET Framework Windows Forms denetimini bir MFC kapsayıcısındaki başlatır.  
  
 Bir .NET Framework veri türü yönteminin ilk aşırı kabul *pType* böylece MFC bu türdeki yeni bir nesne örneğini oluşturabilirsiniz. *pType* olmalıdır bir [türü](https://msdn.microsoft.com/en-us/library/system.type) veri türü.  
  
 Temel bir Windows Forms denetimi yöntemi ikinci yüklemesini oluşturur `TManagedControl` şablon parametresinin `CWinFormsControl` sınıfı. Denetimin konumunu ve boyutunu temel `RECT` yapısı metoduna geçirilen. Yalnızca *dwStyle* stilleri için önemlidir.  
  
 Üçüncü aşırı yükleme yöntemi, yok etme ve konum, z düzenini ve stili varsayılarak statik bir denetimi değiştiren bir Windows Forms denetimi oluşturur. Statik denetimi, yalnızca Windows Forms denetimi için bir yer tutucu olarak görev yapar. Denetim oluştururken, bu aşırı stilleri birleştirir *dwStyle* statik denetimin kaynak stilleri.  
  
 Dördüncü aşırı yükleme yöntemi, önceden oluşturulmuş bir Windows Forms denetiminde geçirmenizi sağlar *pControl* , MFC kaydırılır. Aynı türde olmalıdır `TManagedControl` şablon parametresinin `CWinFormsControl` sınıfı.  
  
 Bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md) Windows Form kullanma örnekleri için denetler.  
  
##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl  
 Bir MFC Windows Forms denetimi sarmalayıcı nesnesi oluşturur.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Windows Forms denetimi çağırdığınızda örneği [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrol"></a>  CWinFormsControl::GetControl  
 Windows Forms denetimi için bir işaretçi alır.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi Windows Forms denetimini döndürür.  
  
### <a name="example"></a>Örnek  
  Bkz: [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle  
 Windows Forms denetimi için bir tanıtıcı alır.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows Forms denetimi için bir işleyici döner.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetControlHandle` .NET Framework denetim özelliklerinde saklanan bir pencere tanıtıcının döndüren bir yardımcı yöntemdir. Pencere tanıtıcı değeri kopyalanır [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) çağrı sırasında [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).  
  
##  <a name="operator_-_gt"></a>  CWinFormsControl::operator-&gt;  
 Değiştirir [CWinFormsControl::GetControl](#getcontrol) ifadelerde.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç değiştirir kullanışlı bir sözdizimi sağlar `GetControl` ifadelerde.  
  
 Windows Forms hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl ^  
 Bir Windows Forms denetimi için bir işaretçi olarak bir tür çevirir.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç geçirir `CWinFormsControl<TManagedControl>` bir Windows Forms denetimi için bir işaretçi kabul işlevlere.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinFormsDialog sınıfı](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)
