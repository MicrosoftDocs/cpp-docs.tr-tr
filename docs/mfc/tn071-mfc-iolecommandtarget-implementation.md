---
title: 'TN071: MFC IOleCommandTarget uygulaması | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21745762fb6f6eb1eb324013db12207c4b3b81d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: MFC IOleCommandTarget Uygulaması
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 `IOleCommandTarget` Nesneleri ve kapsayıcılarına birbirlerine komutları gönderilmesi için arabirim sağlar. Örneğin, bir nesnenin araç çubukları komutları için düğmeler gibi içerebilir **yazdırma**, **Baskı Önizleme**, **kaydetmek**, `New`, ve **yakınlaştırma**. Böyle bir nesnenin katıştırılmış varsa destekleyen bir kapsayıcıda `IOleCommandTarget`, nesne düğmeleri etkinleştirebilir ve kullanıcı bunları tıklatıldığında işlemek için kapsayıcısı komutları iletin. Bir kapsayıcı kendisini yazdırmak için katıştırılmış nesne istediyseniz, bu istek bir komutu aracılığıyla göndererek kolaylaştırır `IOleCommandTarget` katıştırılmış nesnenin arabirimi.  
  
 `IOleCommandTarget` İstemci tarafından bir sunucuda yöntemleri çağırmak için kullanılan bir Otomasyon benzeri arabirimiyle olmamasıdır. Ancak, kullanarak `IOleCommandTarget` programcıları genellikle pahalı kullanmanız gerekmez çünkü Otomasyon arabirimleri çağrıları yapma yükünü kaydeder `Invoke` yöntemi `IDispatch`.  
  
 MFC'de, `IOleCommandTarget` arabirimi komutları sunucusuna gönderilmesi etkin belge kapsayıcıları izin vermek için etkin belge sunucuları tarafından kullanılır. Etkin belge sunucu sınıfı `CDocObjectServerItem`, MFC arabirimi eşlemelerini kullanır (bkz [TN038: MFC/OLE IUnknown uygulaması](../mfc/tn038-mfc-ole-iunknown-implementation.md)) uygulamak için `IOleCommandTarget` arabirimi.  
  
 `IOleCommandTarget` Ayrıca uygulanan **COleFrameHook** sınıfı. **COleFrameHook** olan yerinde çerçeve penceresi işlevselliğini uygulayan belgelenmemiş MFC sınıfı düzenleme kapsayıcıları. **COleFrameHook** MFC arabirimi eşlemeleri uygulamak için de kullanır `IOleCommandTarget` arabirimi. **COleFrameHook**'s uyarlamasını `IOleCommandTarget` OLE komutları iletir `COleDocObjectItem`-etkin belge kapsayıcıları türetilmiş. Kapsanan etkin belgeyi sunucularından iletileri almak tüm MFC etkin belge kapsayıcı sağlar.  
  
## <a name="mfc-ole-command-maps"></a>MFC OLE komutu eşlemeleri  
 MFC geliştiriciler yararlanabilir `IOleCommandTarget` MFC OLE kullanarak eşlemeleri komutu. Komut eşleme içeren sınıf üyesi işlevleri için OLE komutları eşleştirmek için kullanılabilir olduğundan ileti eşlemeleri gibi OLE komutu eşlemeleri var. Bunun çalışmasını sağlamak için makroları OLE komut grubunun işlemek istediğiniz komut, OLE komut ve komut Kimliğini belirtmek için komut eşlemesinde yerleştirin [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) OLE komutu alındığında gönderilecek ileti. MFC önceden tanımlı makrolar bir dizi standart OLE komutları için de sağlar. Standart OLE listesi için tasarlanmış komutları Microsoft Office uygulamalarıyla kullanmak, docobj.h içinde tanımlanan OLECMDID numaralandırma bakın.  
  
 OLE komutu OLE komutu eşleme içeren bir MFC uygulaması tarafından alındığında, MFC Uygulama OLE komutu haritasını istenen komut için komut kimliği ve komut grubu bulmayı dener. Bir eşleşme bulunursa, bir **WM_COMMAND** istenen komut kimliği komutu eşleme içeren bir uygulama için ileti gönderilemiyor. (Açıklamasına bakın `ON_OLECMD` aşağıda.) Bu şekilde, bir uygulamaya gönderilen OLE komutları içine açık **WM_COMMAND** MFC tarafından iletileri. **WM_COMMAND** iletileri sonra MFC standardını kullanarak uygulamanın ileti eşlemeleri yönlendirilen [komut yönlendirme](../mfc/command-routing.md) mimarisi.  
  
 İleti eşlemeleri, MFC OLE komutu eşlemeleri ClassWizard tarafından desteklenmez. MFC geliştiriciler OLE komut harita desteği ve OLE komutu eşleme girdilerini el ile eklemeniz gerekir. OLE komutu eşlemeleri bulunduğu herhangi bir sınıf MFC etkin belge sunucuları eklenebilir **WM_COMMAND** ileti yönlendirme zinciri etkin belgeyi bir kapsayıcıda yerinde etkin olduğu zaman. Bu sınıfların türetilmiş uygulamanın sınıfları içerir [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md), ve [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md). Etkin belge kapsayıcıları OLE komutu eşlemeleri yalnızca eklenebilir [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)-türetilmiş sınıf. Etkin belge kapsayıcıları, ayrıca, **WM_COMMAND** iletileri yalnızca gönderilen ileti eşlemesi için `COleDocObjectItem`-türetilmiş sınıf.  
  
## <a name="ole-command-map-macros"></a>OLE komutu eşleme makroları  
 Komut eşleme işlevselliği sınıfınıza eklemek için aşağıdaki makroları kullanın:  
  
```  
 
DECLARE_OLECMD_MAP ()  
 
```  
  
 Bu makrosu komutu eşleme içeren sınıf (genellikle başlık dosyasındaki) sınıf bildirimi gider.  
  
```  
 
BEGIN_OLECMD_MAP(
theClass  ,   baseClass)  
 
```  
  
 `theClass`  
 Komut eşleme içeren sınıfın adı.  
  
 `baseClass`  
 Komut eşleme içeren sınıfın temel sınıf adı.  
  
 Bu makrosu komutu harita başlangıcını işaretler. Komut eşleme içeren sınıf için uygulama dosyasında bu makrosu kullanın.  
  
```  
 
END_OLECMD_MAP()  
 
```  
  
 Bu makrosu komutu harita sonunu işaretler. Komut eşleme içeren sınıf için uygulama dosyasında bu makrosu kullanın. Bu makrosu her zaman izlemelisiniz **BEGIN_OLECMD_MAP** makrosu.  
  
```  
 
ON_OLECMD(
pguid  ,   
olecmdid  ,
    id)  
 
```  
  
 `pguid`  
 İşaretçi OLE komutunun komut grubu GUID. Bu parametre **NULL** standart OLE komut grubu.  
  
 *olecmdid*  
 Çağrılacak komut OLE komut kimliği.  
  
 `id`  
 Kimliği **WM_COMMAND** Bu OLE komutu çağrıldığında komutu eşleme içeren bir uygulama için gönderilecek ileti.  
  
 Kullanım `ON_OLECMD` makrosu girdiler için OLE eklemek için komut eşlemesindeki komutları işlemek istediğiniz. OLE komutları alındığında bunlar dönüştürülecek belirtilen **WM_COMMAND** ileti ve komut yönlendirme standart MFC mimarisi kullanarak uygulama ileti eşlemesi üzerinden yönlendirilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, OLE komut işleme yeteneği işlemek için bir MFC etkin belge sunucusuna eklemek gösterilmiştir [OLECMDID_PRINT](http://msdn.microsoft.com/library/windows/desktop/ms691264) OLE komutu. Bu örnek AppWizard etkin belgeyi sunucu bir MFC uygulaması oluşturmak için kullanılan varsayar.  
  
1.  İçinde `CView`-sınıfının üstbilgi türetilmiş dosya, ekleme `DECLARE_OLECMD_MAP` sınıf bildiriminin makrosuna.  
  
    > [!NOTE]
    >  Kullanım `CView`-bulunduğu etkin belge sunucusu sınıflarda biri olduğundan türetilmiş sınıf **WM_COMMAND** ileti yönlendirme zinciri.  
  
 ```  
    class CMyServerView : public CView  
 {  
    protected: // create from serialization only  
    CMyServerView();
DECLARE_DYNCREATE(CMyServerView)  
    DECLARE_OLECMD_MAP() 
 . . .  
 };  
 ```  
  
2.  Uygulama dosyasında `CView`-türetilmiş sınıf, ekleme `BEGIN_OLECMD_MAP` ve `END_OLECMD_MAP` makroları:  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
 
    END_OLECMD_MAP() 
 ```  
  
3.  Standart OLE yazdırma komutunu işlemek için ekleme bir [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) standart yazdırma komutu için OLE komut Kimliğini belirtme komutu eşlemesine makrosu ve **ıd_fıle_prınt** için **WM_COMMAND**  Kimliği **Id_fıle_prınt** yazdırma komut kimliği AppWizard oluşturulan MFC uygulamaları tarafından kullanılan standart:  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView,
    CView)  
    ON_OLECMD(NULL,
    OLECMDID_PRINT,
    ID_FILE_PRINT) 
    END_OLECMD_MAP() 
 ```  
  
 Afxdocob.h içinde tanımlanan standart OLE komut makroları birini yerine kullanılabilir Not `ON_OLECMD` makrosu çünkü **OLECMDID_PRINT** bir standart OLE komut kimliği. `ON_OLECMD_PRINT` Makrosu yerine getirmek gibi aynı görevi `ON_OLECMD` yukarıda gösterilen makrosu.  
  
 Bir kapsayıcı uygulaması, bu sunucu gönderdiğinde bir **OLECMDID_PRINT** sunucunun aracılığıyla komutu `IOleCommandTarget` arabirimini, komut işleyici yazdırma MFC Uygulama yazdırmak sunucunun neden Server'da çağrılan. Etkin belge kapsayıcısı kodu Yukarıdaki adımlarda eklenen yazdırma komutunu Çağır şunun gibi görünür:  
  
```  
void CContainerCntrItem::DoOleCmd()  
{  
    IOleCommandTarget *pCmd = NULL;  
    HRESULT hr = E_FAIL;  
    OLECMD ocm={OLECMDID_PRINT, 0};  
 
    hr = m_lpObject->QueryInterface(IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));

    if(FAILED(hr)) 
    return; 
 
    hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);

    if(SUCCEEDED(hr)&& (ocm.cmdf& OLECMDF_ENABLED))  
 { *//Command is available and enabled so call it  
    COleVariant vIn;  
    COleVariant vOut;  
    hr = pCmd->Exec(NULL, OLECMDID_PRINT,  
    OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);

    ASSERT(SUCCEEDED(hr));

 }  
    pCmd->Release();

} 
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

