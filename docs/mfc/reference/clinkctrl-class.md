---
title: "CLinkCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
dev_langs:
- C++
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6834190d7693e60f80285b04a04c484313d3c2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="clinkctrl-class"></a>CLinkCtrl sınıfı
Windows ortak SysLink denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|Oluşturan bir `CLinkCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CLinkCtrl::Create](#create)|Bir bağlantı denetimi oluşturur ve ona ekler bir `CLinkCtrl` nesnesi.|  
|[CLinkCtrl::CreateEx](#createex)|Genişletilmiş stilleri ile bir bağlantı denetimi oluşturur ve ekler bir `CLinkCtrl` nesnesi.|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Bağlantı denetimi ideal yüksekliğini alır.|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|Bağlantı metni bağlantının belirtilen genişlik bağlı olarak geçerli bağlantı denetimi için tercih edilen yüksekliğini hesaplar.|  
|[CLinkCtrl::GetItem](#getitem)|Durumları ve bir bağlantı denetimi öğesi özniteliklerini alır.|  
|[CLinkCtrl::GetItemID](#getitemid)|Bir bağlantı denetimi öğesi Kimliğini alır.|  
|[CLinkCtrl::GetItemState](#getitemstate)|Bağlantı Denetim öğesi durumunu alır.|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|Bağlantı denetimi öğesi tarafından temsil edilen URL'sini alır.|  
|[CLinkCtrl::HitTest](#hittest)|Kullanıcı belirtilen bağlantı tıklatıldığında olup olmadığını belirler.|  
|[CLinkCtrl::SetItem](#setitem)|Bir bağlantı denetimi öğesi özniteliklerini ve durumlarını ayarlar.|  
|[CLinkCtrl::SetItemID](#setitemid)|Bir bağlantı denetimi öğesi Kimliğini ayarlar.|  
|[CLinkCtrl::SetItemState](#setitemstate)|Bağlantı Denetim öğesi durumunu ayarlar.|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|Bağlantı denetimi öğesi tarafından temsil edilen URL'sini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir "bağlantı denetimi" Köprü metin bağlantılarından bir pencerede katıştırmak için kolay bir yol sağlar. Gerçek denetim işaretlenmiş metin oluşturur ve kullanıcının katıştırılmış bir bağlantıyı tıklattığında uygun uygulamaları başlatma bir penceredir. Birden çok bağlantı içinde bir denetim desteklenir ve sıfır tabanlı dizini tarafından erişilebilir.  
  
 Bu denetim (ve bu nedenle `CLinkCtrl` sınıfı) yalnızca Windows XP altında ve sonraki sürümlerde çalışan programlar için kullanılabilir.  
  
 Daha fazla bilgi için bkz: [SysLink denetim](http://msdn.microsoft.com/library/windows/desktop/bb760706) Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="clinkctrl"></a>CLinkCtrl::CLinkCtrl  
 Oluşturan bir `CLinkCtrl` nesnesi.  
  
```  
CLinkCtrl();
```  
  
##  <a name="create"></a>CLinkCtrl::Create  
 Bir bağlantı denetimi oluşturur ve ona ekler bir `CLinkCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszLinkMarkup`  
 İşaretli görüntülenecek metni içeren sıfır ile sonlandırılan bir dize işaretçi. Daha fazla bilgi için konusundaki "Biçimlendirme ve bağlantı erişim" bölümüne bakın [SysLink denetimleri genel bakış](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 `dwStyle`  
 Bağlantı denetimin stilini belirtir. Herhangi bir bileşimini denetim stilleri uygulayın. Bkz: [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) içinde `Windows SDK` daha fazla bilgi için.  
  
 `rect`  
 Bağlantı denetimin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](../../mfc/reference/rect-structure1.md) yapısı.  
  
 `pParentWnd`  
 Bağlantı denetimin üst penceresi belirtir. Değil olmalıdır `NULL`.  
  
 `nID`  
 Bağlantı denetimin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`başlatma başarılı olduysa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CLinkCtrl` iki adımda nesne. İlk olarak, Oluşturucusu arayın ve ardından arama `Create`, hangi bağlantı denetimi oluşturur ve ona ekler `CLinkCtrl` nesnesi. Genişletilmiş windows stilleri denetimi ile kullanmak istiyorsanız, çağrı [CLinkCtrl::CreateEx](#createex) yerine `Create`.  
  
 İkinci biçiminde `Create` yöntemi kullanım dışıdır. Belirtir ilk formu kullanın `lpszLinkMarkup` parametresi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde adlı iki değişken tanımlar `m_Link1` ve `m_Link2`, iki bağlantı denetimlerini erişmek için kullanılır.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği başka bir bağlantı denetimi konumunu temelinde bir bağlantı denetimi oluşturur. Uygulamanız başladığında kaynak yükleyicisi ilk bağlantı denetimi oluşturur. Uygulamanızı OnInitDialog yöntemi girdiğinde, ilk bağlantı denetimi konumunu göre ikinci bağlantı denetimi oluşturun. Ardından görüntülediği metnin sığması için ikinci bağlantı denetimi yeniden boyutlandırın.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CLinkCtrl::CreateEx  
 Genişletilmiş stilleri ile bir bağlantı denetimi oluşturur ve ekler bir `CLinkCtrl` nesnesi.  
  
```  
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwExStyle,  
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszLinkMarkup`  
 İşaretli görüntülenecek metni içeren sıfır ile sonlandırılan bir dize işaretçi. Daha fazla bilgi için konusundaki "Biçimlendirme ve bağlantı erişim" bölümüne bakın [SysLink denetimleri genel bakış](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 `dwExStyle`  
 Bağlantı denetimi genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri listesi için bkz: `dwExStyle` parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 `dwStyle`  
 Bağlantı denetimin stilini belirtir. Herhangi bir bileşimini denetim stilleri uygulayın. Daha fazla bilgi için bkz: [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) Windows SDK.  
  
 `rect`  
 Bağlantı denetimin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](../../mfc/reference/rect-structure1.md) yapısı.  
  
 `pParentWnd`  
 Bağlantı denetimin üst penceresi belirtir. Değil olmalıdır `NULL`.  
  
 `nID`  
 Bağlantı denetimin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`başlatma başarılı olduysa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [oluşturma](#create) genişletilmiş Windows stili sabitleri uygulamak için.  
  
 İkinci biçiminde `CreateEx` yöntemi kullanım dışıdır. Belirtir ilk formu kullanın `lpszLinkMarkup` parametresi.  
  
##  <a name="getidealheight"></a>CLinkCtrl::GetIdealHeight  
 Bağlantı denetimi ideal yüksekliğini alır.  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimin piksel cinsinden ideal yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [LM_GETIDEALHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb760716), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="getidealsize"></a>CLinkCtrl::GetIdealSize  
 Bağlantı metni bağlantının belirtilen genişlik bağlı olarak geçerli bağlantı denetimi için tercih edilen yüksekliğini hesaplar.  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`cxMaxWidth`|En büyük genişliği. piksel cinsinden bağlantı.|  
|[Çıkış] *`pSize`|Windows için bir işaretçi [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı. Bu yöntem döndürüldüğünde, `cy` üyesi `SIZE` yapısı tarafından belirtilen bağlantı metni genişliği için ideal bağlantı metin yükseklik içeren `cxMaxWidth`. `cx` Yapısı üyesi için gerekli olan bağlantı metin genişliği içerir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tercih edilen bağlantı metnini, piksel cinsinden yüksekliği. Dönüş değeri değeri ile aynıdır `cy` üyesi `SIZE` yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir örnek için `GetIdealSize` yöntemi, örnekte bkz [CLinkCtrl::Create](#create).  
  
 Bu yöntem gönderir [LM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760718) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getitem"></a>CLinkCtrl::GetItem  
 Durumları ve bir bağlantı denetimi öğesi özniteliklerini alır.  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Bir işaretçi bir [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) öğesi bilgi almak için yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="getitemid"></a>CLinkCtrl::GetItemID  
 Bir bağlantı denetimi öğesi Kimliğini alır.  
  
```  
BOOL GetItemID(
    int iLink,  
    CString& strID) const;  
  
BOOL GetItemID(
    int iLink,  
    LPWSTR szID,  
    UINT cchID) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `iLink`  
 Bir bağlantı denetimi öğesi dizini.  
  
 *strID*  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) belirtilen öğeyi Kimliğini içeren nesne.  
  
 *szID*  
 Belirtilen öğe Kimliğini içeren null ile sonlandırılmış bir dize.  
  
 *cchID*  
 Karakter cinsinden boyutu *szID* arabellek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
> [!NOTE]
>  Bu işlev, aynı zamanda döndürür **FALSE** varsa arabelleğin *szID veya strID* değerinden küçük **MAX_LINKID_TEXT**.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bağlantı denetimi öğesi Kimliğini alır. Daha fazla bilgi için bkz: Win32 ileti [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) Windows SDK'sındaki.  
  
##  <a name="getitemstate"></a>CLinkCtrl::GetItemState  
 Bağlantı Denetim öğesi durumunu alır.  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `iLink`  
 Bir bağlantı denetimi öğesi dizini.  
  
 `pnState`  
 Belirtilen durum öğesinin değeri.  
  
 `stateMask`  
 Almak için hangi durumu öğesi açıklayan bayrakları birleşimi. Açıklamasını değerlerinin listesi için bkz: **durumu** üye [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) yapısı. Bu izin için izin verilen öğeleri aynıdır **durumu**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bağlantı denetimi öğesinin belirtilen durum öğenin değerini alır. Daha fazla bilgi için bkz: Win32 ileti [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) Windows SDK'sındaki.  
  
##  <a name="getitemurl"></a>CLinkCtrl::GetItemUrl  
 Bağlantı denetimi öğesi tarafından temsil edilen URL'sini alır.  
  
```  
BOOL GetItemUrl(
    int iLink,  
    CString& strUrl) const;  
  
BOOL GetItemUrl(
    int iLink,  
    LPWSTR szUrl,  
    UINT cchUrl) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `iLink`  
 Bir bağlantı denetimi öğesi dizini.  
  
 `strUrl`  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) tarafından belirtilen öğeyi temsil URL içeren bir nesne  
  
 `szUrl`  
 Belirtilen öğe tarafından temsil edilen URL'sini içeren null sonlandırılmış bir dize  
  
 *cchUrl*  
 Karakter cinsinden boyutu *szURL* arabellek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
> [!NOTE]
>  Bu işlev, aynı zamanda döndürür **FALSE** varsa arabelleğin *szUrl veya strUrl* değerinden küçük **MAX_LINKID_TEXT**.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen bağlantı denetimi öğesi tarafından temsil edilen URL'sini alır. Daha fazla bilgi için bkz: Win32 ileti [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) Windows SDK'sındaki.  
  
##  <a name="hittest"></a>CLinkCtrl::HitTest  
 Kullanıcı belirtilen bağlantıyı tıklattığında, belirler.  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *phti*  
 İşaretçi bir **LHITTESTINFO** kullanıcı tıkladığınız bağlantı hakkındaki tüm bilgileri içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [LM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb760722), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setitem"></a>CLinkCtrl::SetItem  
 Bir bağlantı denetimi öğesi özniteliklerini ve durumlarını ayarlar.  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Bir işaretçi bir [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) ayarlamak için bilgileri içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi Win32 ileti davranışını uygulayan [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setitemid"></a>CLinkCtrl::SetItemID  
 Bir bağlantı denetimi öğesi Kimliğini alır.  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>Parametreler  
 `iLink`  
 Bir bağlantı denetimi öğesi dizini.  
  
 *szID*  
 Belirtilen öğe Kimliğini içeren null ile sonlandırılmış bir dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bağlantı denetimi öğesi Kimliğini ayarlar. Daha fazla bilgi için bkz: Win32 ileti [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) Windows SDK'sındaki.  
  
##  <a name="setitemstate"></a>CLinkCtrl::SetItemState  
 Bağlantı Denetim öğesi durumunu alır.  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>Parametreler  
 `iLink`  
 Bir bağlantı denetimi öğesi dizini.  
  
 `pnState`  
 Ayarlanan belirli durumda öğesinin değeri.  
  
 `stateMask`  
 Ayarlanan durumu öğesi açıklayan bayrakları birleşimi. Açıklamasını değerlerinin listesi için bkz: **durumu** üye [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) yapısı. Bu izin için izin verilen öğeleri aynıdır **durumu**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen durum öğesi'nin belirli bağlantı denetimi öğesi değerini ayarlar. Daha fazla bilgi için bkz: Win32 ileti [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) Windows SDK'sındaki.  
  
##  <a name="setitemurl"></a>CLinkCtrl::SetItemUrl  
 Bağlantı denetimi öğesi tarafından temsil edilen URL'sini ayarlar.  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>Parametreler  
 `iLink`  
 Bir bağlantı denetimi öğesi dizini.  
  
 `szUrl`  
 Belirtilen öğe tarafından temsil edilen URL'sini içeren null sonlandırılmış bir dize  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen bağlantı denetimi öğesi tarafından temsil edilen URL'sini ayarlar. Daha fazla bilgi için bkz: Win32 ileti [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
