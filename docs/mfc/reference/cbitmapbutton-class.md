---
title: CBitmapButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
dev_langs:
- C++
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ba2a3f54ff39341c43ee497fcccda43cd3625fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358361"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton sınıfı
Metin yerine eşlemli görüntülerle etiketli basma düğmesi denetimleri oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Oluşturan bir `CBitmapButton` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBitmapButton::AutoLoad](#autoload)|Bir nesne ile bir iletişim kutusunda bir düğme ilişkilendirir `CBitmapButton` sınıfı, ada göre bitmap(s) yükler ve bit eşlem sığması için düğmeyi boyutlandırır.|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Bir veya daha fazla adlandırılmış bit eşlem kaynaklar uygulamanın kaynak dosyasından yükleniyor ve nesnesine bit eşlemler ekleme nesnesini başlatır.|  
|[CBitmapButton::SizeToContent](#sizetocontent)|Bit eşlem uyum sağlamak için düğmeyi boyutlandırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CBitmapButton` nesneleri içeren bir düğme varsayabilirsiniz farklı durumları için görüntüleri içeren en fazla dört bit eşlemler: Yukarı (veya normal), aşağı (veya seçili) odaklı ve devre dışı. Yalnızca ilk bit eşlem gereklidir; diğerleri isteğe bağlıdır.  
  
 Bit eşlem düğme resimlerini görüntü yanı sıra görüntünün çevresine kenarlık içerir. Kenarlığın genellikle düğmenin durumunu gösteren bir rol oynar. Örneğin, bit eşlem odaklanmış durumu için genellikle bir yukarı durumu için ancak kesikli dikdörtgen iç kenarlık veya kenarlık kalın düz satırında gibidir. Devre dışı genellikle durum için bit eşlem yukarı durumu ancak daha düşük karşıtlıklı (gibi bir soluk veya gri menü seçimi) sahip bir benzer.  
  
 Bu bit eşlemler herhangi bir boyutta olabilir ancak bit eşlem yukarı durumu için aynı boyutta değilmiş gibi tüm kabul edilir.  
  
 Çeşitli uygulamalar bitmap görüntüleri farklı birleşimlerini talep:  
  
|Ayarlama|Aşağı|Odaklanmış|Devre dışı|Uygulama|  
|--------|----------|-------------|--------------|-----------------|  
|×||||Bit eşlem|  
|×|×|||Olmadan düğmesini **WS_TABSTOP** stili|  
|×|×|×|×|Tüm durumları ile iletişim düğmesi|  
|×|×|×||İletişim düğmesi ile **WS_TABSTOP** stili|  
  
 Bir bit eşlem düğme denetimi oluştururken ayarlama **BS_OWNERDRAW** düğmesini sahip tarafından çizilmiş olduğunu belirtmek için stili. Bu göndermek Windows neden olur `WM_MEASUREITEM` ve `WM_DRAWITEM` düğme; iletilerde framework bu iletileri işleme ve düğmenin görünümünü sizin için yönetir.  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Pencerenin istemci alanında bir bit eşlem düğme denetimi oluşturmak için  
  
1.  Düğme için dörde bitmap görüntüleri oluşturun.  
  
2.  Oluşturmak [CBitmapButton](#cbitmapbutton) nesnesi.  
  
3.  Çağrı [oluşturma](../../mfc/reference/cbutton-class.md#create) Windows düğme denetimi oluşturmak ve ona eklemek için işlevi `CBitmapButton` nesnesi.  
  
4.  Çağrı [LoadBitmaps](#loadbitmaps) bit eşlem düğmesi oluşturulan sonra bit eşlem kaynakları yüklemek için üye işlevi.  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Bir iletişim kutusunda bir bit eşlem düğme denetimi eklemek için  
  
1.  Düğme için dörde bitmap görüntüleri oluşturun.  
  
2.  Bit eşlem düğmesi istediğiniz konumlandırılmış bir sahip çizim düğmesi ile bir iletişim şablonunu oluşturun. Şablondaki düğmesi boyutu önemli değildir.  
  
3.  Düğmenin resim yazısı gibi bir değere ayarlayın " **MYIMAGE**" ve düğmesi için simge tanımlayın **IDC_MYIMAGE**.  
  
4.  Uygulamanızın kaynak komut dosyası, her harf "U," "D" "F" eklenerek oluşturulan kimliği düğmesi için oluşturulmuş görüntülerin vermek veya "X" (yukarı, aşağı, odaklı ve devre dışı için) düğmesini yazısının için kullanılan dize için adım 3. Düğme resim yazısı " **MYIMAGE**," Örneğin, kimlikleri olur " **MYIMAGEU**," " **MYIMAGED**," " **MYIMAGEF**," ve " **MYIMAGEX**. " **Gerekir** , bit eşlemler çift tırnak işareti içinde Kimliğini belirtin. Aksi takdirde Kaynak Düzenleyici bir tamsayı kaynağa atar ve MFC görüntü yüklenirken başarısız olur.  
  
5.  Uygulamanızın iletişim sınıfında (türetilmiş `CDialog`), ekleme bir `CBitmapButton` üye nesne.  
  
6.  İçinde `CDialog` nesnenin [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) rutin, çağrı `CBitmapButton` nesnenin [AutoLoad](#autoload) işlev, düğme denetim kimliği parametreleri olarak kullanma ve `CDialog` nesnenin **bu** işaretçi.  
  
 Windows bildirim iletileri gibi işlemek istiyorsanız **BN_CLICKED**, üst bir bit eşlem düğme denetimi tarafından gönderilen (öğesinden türetilmiş bir sınıf genellikle **CDialog)**, eklemek `CDialog`-türetilen her ileti için ileti eşleme girişi ve ileti işleyicisi üye işlevi nesne. Tarafından gönderilen bildirimler bir `CBitmapButton` nesne aynıdır olanlar tarafından gönderilen bir [CButton](../../mfc/reference/cbutton-class.md) nesnesi.  
  
 Sınıf [CToolBar](../../mfc/reference/ctoolbar-class.md) bit eşlem düğmeleri için farklı bir yaklaşım alır.  
  
 Daha fazla bilgi için `CBitmapButton`, bkz: [denetimleri](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="autoload"></a>  CBitmapButton::AutoLoad  
 Bir nesne ile bir iletişim kutusunda bir düğme ilişkilendirir `CBitmapButton` sınıfı, ada göre bitmap(s) yükler ve bit eşlem sığması için düğmeyi boyutlandırır.  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Düğme denetim kimliği.  
  
 `pParent`  
 Düğme sahibi nesnesine işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `AutoLoad` işlevi bir bit eşlem düğmesi olarak bir iletişim kutusunda bir sahip çizim düğmesini başlatılamadı. Bu işlev kullanma yönergeleri için açıklamalar olan `CBitmapButton` sınıfı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>  CBitmapButton::CBitmapButton  
 Oluşturur bir `CBitmapButton` nesnesi.  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>Açıklamalar  
 C++ oluşturduktan sonra `CBitmapButton` nesne, çağrı [CButton::Create](../../mfc/reference/cbutton-class.md#create) Windows düğme denetimi oluşturmak ve ona eklemek için `CBitmapButton` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>  CBitmapButton::LoadBitmaps  
 Bit eşlem görüntüleri veya kaynak adları veya kimlik numaraları tarafından kullanılamaz olduğunda tanımlanan yüklemek istediğinizde bu işlevi kullanın `AutoLoad` Örneğin, bir iletişim kutusu parçası olmayan bir bit eşlem düğmesi oluşturma çünkü işlev.  
  
```  
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,  
    LPCTSTR lpszBitmapResourceSel = NULL,  
    LPCTSTR lpszBitmapResourceFocus = NULL,  
    LPCTSTR lpszBitmapResourceDisabled = NULL);

 
BOOL LoadBitmaps(
    UINT nIDBitmapResource,  
    UINT nIDBitmapResourceSel = 0,  
    UINT nIDBitmapResourceFocus = 0,  
    UINT nIDBitmapResourceDisabled = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszBitmapResource*  
 Bir bit eşlem düğmenin normal veya "çalışır" durumda bit eşlem adını içeren null sonlandırılmış bir dize noktalarına. Gerekli.  
  
 *lpszBitmapResourceSel*  
 Bir bit eşlem düğmesi seçilen için bit eşlem adını içeren null ile sonlandırılmış dize veya "kapalı" durumu noktaları. Olabilir **NULL**.  
  
 *lpszBitmapResourceFocus*  
 Bir bit eşlem düğmenin için bit eşlem adını içeren null sonlandırılmış bir dize noktalarına durumu odaklanır. Olabilir **NULL**.  
  
 *lpszBitmapResourceDisabled*  
 Bir bit eşlem düğmenin için bit eşlem adını içeren null sonlandırılmış bir dize noktalarına durumu devre dışı. Olabilir **NULL**.  
  
 *nIDBitmapResource*  
 Bit eşlem kaynak için bir bit eşlem düğmenin normal veya "çalışır" durumda kaynak kimliği sayısını belirtir. Gerekli.  
  
 *nIDBitmapResourceSel*  
 Bir bit eşlem düğmesi seçilen için veya "kapalı" durumu bit eşlem kaynağı kaynak kimliği sayısını belirtir. 0 olabilir.  
  
 *nIDBitmapResourceFocus*  
 Bir bit eşlem düğmenin odaklanmış durumu için bit eşlem kaynağının kaynak kimliği numarasını belirtir. 0 olabilir.  
  
 *nIDBitmapResourceDisabled*  
 Bir bit eşlem düğmenin devre dışı durumunu bit eşlem kaynağın kaynak kimliği numarasını belirtir. 0 olabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>  CBitmapButton::SizeToContent  
 Bit eşlem boyutunu bit eşlem düğmeye yeniden boyutlandırmak için bu işlevini çağırın.  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLTEST](../../visual-cpp-samples.md)   
 [CButton sınıfı](../../mfc/reference/cbutton-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

