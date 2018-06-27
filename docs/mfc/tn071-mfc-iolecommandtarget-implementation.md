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
ms.openlocfilehash: c3e2a4fa51525417be8ab6ae2ef1f4f2f5470185
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957139"
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: MFC IOleCommandTarget Uygulaması
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 `IOleCommandTarget` Nesneleri ve kapsayıcılarına birbirlerine komutları gönderilmesi için arabirim sağlar. Örneğin, bir nesnenin araç çubukları komutları için düğmeler gibi içerebilir `Print`, `Print Preview`, `Save`, `New`, ve `Zoom`. Böyle bir nesnenin katıştırılmış varsa destekleyen bir kapsayıcıda `IOleCommandTarget`, nesne düğmeleri etkinleştirebilir ve kullanıcı bunları tıklatıldığında işlemek için kapsayıcısı komutları iletin. Bir kapsayıcı kendisini yazdırmak için katıştırılmış nesne istediyseniz, bu istek bir komutu aracılığıyla göndererek kolaylaştırır `IOleCommandTarget` katıştırılmış nesnenin arabirimi.  
  
 `IOleCommandTarget` İstemci tarafından bir sunucuda yöntemleri çağırmak için kullanılan bir Otomasyon benzeri arabirimiyle olmamasıdır. Ancak, kullanarak `IOleCommandTarget` programcıları genellikle pahalı kullanmanız gerekmez çünkü Otomasyon arabirimleri çağrıları yapma yükünü kaydeder `Invoke` yöntemi `IDispatch`.  
  
 MFC'de, `IOleCommandTarget` arabirimi komutları sunucusuna gönderilmesi etkin belge kapsayıcıları izin vermek için etkin belge sunucuları tarafından kullanılır. Etkin belge sunucu sınıfı `CDocObjectServerItem`, MFC arabirimi eşlemelerini kullanır (bkz [TN038: MFC/OLE IUnknown uygulaması](../mfc/tn038-mfc-ole-iunknown-implementation.md)) uygulamak için `IOleCommandTarget` arabirimi.  
  
 `IOleCommandTarget` Ayrıca uygulanan `COleFrameHook` sınıfı. `COleFrameHook` çerçeve penceresi işlevselliğini yerinde düzenleme kapsayıcıların uygulayan bir belgelenmemiş MFC sınıftır. `COleFrameHook` MFC arabirimi eşlemeleri uygulamak için de kullanır `IOleCommandTarget` arabirimi. `COleFrameHook`kişinin uyarlamasını `IOleCommandTarget` OLE komutları iletir `COleDocObjectItem`-etkin belge kapsayıcıları türetilmiş. Kapsanan etkin belgeyi sunucularından iletileri almak tüm MFC etkin belge kapsayıcı sağlar.  
  
## <a name="mfc-ole-command-maps"></a>MFC OLE komutu eşlemeleri  
 MFC geliştiriciler yararlanabilir `IOleCommandTarget` MFC OLE kullanarak eşlemeleri komutu. Komut eşleme içeren sınıf üyesi işlevleri için OLE komutları eşleştirmek için kullanılabilir olduğundan ileti eşlemeleri gibi OLE komutu eşlemeleri var. Bunun çalışmasını sağlamak için makroları OLE komut grubunun işlemek istediğiniz komut, OLE komut ve komut Kimliğini belirtmek için komut eşlemesinde yerleştirin [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) OLE komutu alındığında gönderilecek ileti. MFC önceden tanımlı makrolar bir dizi standart OLE komutları için de sağlar. Standart OLE listesi için tasarlanmış komutları Microsoft Office uygulamalarıyla kullanmak, docobj.h içinde tanımlanan OLECMDID numaralandırma bakın.  
  
 OLE komutu OLE komutu eşleme içeren bir MFC uygulaması tarafından alındığında, MFC Uygulama OLE komutu haritasını istenen komut için komut kimliği ve komut grubu bulmayı dener. Bir eşleşme bulunamazsa, istenen komut kimliği komutu eşleme içeren bir uygulama için bir WM_COMMAND ileti gönderilir. (Açıklamasına bakın `ON_OLECMD` aşağıda.) Bu şekilde, uygulamaya gönderilen OLE komutları WM_COMMAND iletilere MFC tarafından etkinleştirilir. WM_COMMAND iletileri sonra MFC standardını kullanarak uygulamanın ileti eşlemeleri yönlendirilir [komut yönlendirme](../mfc/command-routing.md) mimarisi.  
  
 İleti eşlemeleri, MFC OLE komutu eşlemeleri ClassWizard tarafından desteklenmez. MFC geliştiriciler OLE komut harita desteği ve OLE komutu eşleme girdilerini el ile eklemeniz gerekir. MAPS WM_COMMAND ileti yönlendirme zincirinde sırasında etkin belgeyi olan herhangi bir sınıf MFC etkin belge sunucuları eklenebilir OLE yerinde etkin bir kapsayıcıda komuttur. Bu sınıfların türetilmiş uygulamanın sınıfları içerir [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md), ve [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md). Etkin belge kapsayıcıları OLE komutu eşlemeleri yalnızca eklenebilir [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)-türetilmiş sınıf. Ayrıca, etkin belge kapsayıcıları WM_COMMAND iletileri yalnızca ileti eşlemesi için dağıtılacağı `COleDocObjectItem`-türetilmiş sınıf.  
  
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
  
 *Sınıfın*  
 Komut eşleme içeren sınıfın adı.  
  
 *baseClass*  
 Komut eşleme içeren sınıfın temel sınıf adı.  
  
 Bu makrosu komutu harita başlangıcını işaretler. Komut eşleme içeren sınıf için uygulama dosyasında bu makrosu kullanın.  
  
```  
 
END_OLECMD_MAP()  
 
```  
  
 Bu makrosu komutu harita sonunu işaretler. Komut eşleme içeren sınıf için uygulama dosyasında bu makrosu kullanın. Bu makrosu her zaman BEGIN_OLECMD_MAP makrosu izlemeniz gerekir.  
  
```  
 
ON_OLECMD(
pguid  ,   
olecmdid  ,
    id)  
 
```  
  
 *pguid*  
 İşaretçi OLE komutunun komut grubu GUID. Bu parametre **NULL** standart OLE komut grubu.  
  
 *olecmdid*  
 Çağrılacak komut OLE komut kimliği.  
  
 *id*  
 Bu OLE komutu çağrıldığında komutu eşleme içeren bir uygulama için gönderilecek WM_COMMAND ileti kimliği.  
  
 ON_OLECMD makrosu komutu eşlemesinde işlemek istediğiniz OLE komutları için girişleri eklemek için kullanın. OLE komutları alındığında bunlar belirtilen WM_COMMAND ileti dönüştürülür ve komut yönlendirme standart MFC mimarisi kullanarak uygulama ileti eşlemesi üzerinden yönlendirilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, OLE komut işleme yeteneği işlemek için bir MFC etkin belge sunucusuna eklemek gösterilmiştir [OLECMDID_PRINT](http://msdn.microsoft.com/library/windows/desktop/ms691264) OLE komutu. Bu örnek AppWizard etkin belgeyi sunucu bir MFC uygulaması oluşturmak için kullanılan varsayar.  
  
1.  İçinde `CView`-sınıfının üstbilgi türetilmiş dosyasında, sınıf bildirimi DECLARE_OLECMD_MAP makrosu ekleyin.  
  
    > [!NOTE]
    >  Kullanım `CView`-WM_COMMAND ileti yönlendirme zincirinde etkin belgeyi sunucusundan sınıflarda biri olduğundan türetilmiş sınıf.  
  
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
  
2.  Uygulama dosyasında `CView`-türetilmiş sınıf, BEGIN_OLECMD_MAP ve END_OLECMD_MAP makroları ekleyin:  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
 
    END_OLECMD_MAP() 
 ```  
  
3.  Standart OLE yazdırma komutunu işlemek için ekleme bir [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) standart yazdırma komutu için OLE komut Kimliğini belirtme komutu eşlemesine makrosu ve **ıd_fıle_prınt** WM_COMMAND kimliği için **Id_fıle_prınt** yazdırma komut kimliği AppWizard oluşturulan MFC uygulamaları tarafından kullanılan standart:  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView,
    CView)  
    ON_OLECMD(NULL,
    OLECMDID_PRINT,
    ID_FILE_PRINT) 
    END_OLECMD_MAP() 
 ```  
  
 Afxdocob.h içinde tanımlanan standart OLE komut makroları birini yerine ON_OLECMD makrosu çünkü kullanılabilir olduğunu unutmayın **OLECMDID_PRINT** bir standart OLE komut kimliği. On_olecmd_prınt makrosu yukarıda gösterilen ON_OLECMD makrosu gibi aynı görevi yapabiliriz.  
  
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

