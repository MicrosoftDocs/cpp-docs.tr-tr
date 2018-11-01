---
title: 'TN071: MFC IOleCommandTarget Uygulaması'
ms.date: 06/28/2018
f1_keywords:
- IOleCommandTarget
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
ms.openlocfilehash: dca1183a17fe8f3022f517d1ad0c3932ea272417
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522232"
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: MFC IOleCommandTarget Uygulaması

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

`IOleCommandTarget` Arabirimi nesneleri ve birbirlerine komutları gönderme kapsayıcılarına etkinleştirir. Örneğin, bir nesnenin araç çubukları komutları için düğmeler gibi içerebilir `Print`, `Print Preview`, `Save`, `New`, ve `Zoom`. Böyle bir nesne gömülü değilse destekleyen bir kapsayıcı `IOleCommandTarget`, nesne düğmeleri etkinleştirebilir ve kullanıcı bunları tıklandığında işlemek için kapsayıcı komutları iletin. Bir kapsayıcı IOleCommandTarget komutunu nesnenin istediyseniz, bu komutu aracılığıyla göndererek bu isteği yapabilirsiniz `IOleCommandTarget` kullanılması katıştırılmış nesnenin arabirimi.

`IOleCommandTarget` bir sunucu üzerinde yöntemleri çağırmak için bir istemci tarafından kullanılır, bir Otomasyon benzeri arabirimidir. Ancak, `IOleCommandTarget` programcılar genellikle pahalı kullanmanız gerekmez çünkü Otomasyon arabirimlerini çağrıları yapma ek yükü kaydeder `Invoke` yöntemi `IDispatch`.

MFC'de, `IOleCommandTarget` arabirimi komutları sunucuya gönderme etkin belge kapsayıcıları izin vermek için etkin belge sunucuları tarafından kullanılır. Etkin belge sunucusu sınıfı `CDocObjectServerItem`, MFC arabirim eşlemeleri kullanır (bkz [TN038: MFC/OLE IUnknown uygulaması](../mfc/tn038-mfc-ole-iunknown-implementation.md)) uygulamak için `IOleCommandTarget` arabirimi.

`IOleCommandTarget` Ayrıca, uygulanan `COleFrameHook` sınıfı. `COleFrameHook` yerinde düzenleme kapsayıcıları çerçeve penceresi işlevlerini uygulayan belgelenmemiş bir MFC sınıfı var. `COleFrameHook` MFC arabirim eşlemeleri'uygulamak için de kullanır `IOleCommandTarget` arabirimi. `COleFrameHook`ın uygulaması `IOleCommandTarget` OLE komutları iletir `COleDocObjectItem`-etkin belge kapsayıcıları türetilmiş. Bu, kapsanan etkin belge sunucuları iletileri almak tüm MFC etkin belge kapsayıcı sağlar.

## <a name="mfc-ole-command-maps"></a>MFC OLE komutu eşlemeleri

MFC geliştiriciler yararlanabilir `IOleCommandTarget` komutunu eşlemleri MFC OLE kullanarak. İçin komut eşlemesini içeren sınıfın üye işlevleri OLE komutları eşleştirmek için kullanılabilir olduğundan ileti eşlemeleri gibi OLE komutu eşlemeleri var. Bunun çalışmasını sağlamak için makroları işlemek istediğiniz komut, OLE komut ve komut kimliği OLE komut grubu belirtmek için komut haritada yerleştirin [WM_COMMAND](/windows/desktop/menurc/wm-command) OLE komutunu aldığında gönderilecek ileti. MFC önceden tanımlanmış makrolar bir dizi standart OLE komutları için de sağlar. Standart OLE listesi için tasarlanmış komutları ile Microsoft Office uygulamalarını kullanmaktadır, docobj.h içinde tanımlanan OLECMDID numaralandırma bakın.

Bir OLE komutu bir OLE komut eşlemesini içeren bir MFC uygulaması tarafından alındığında, MFC, OLE komut haritadaki uygulamasının istenen komut komut kimliği ve komut grubunu bulmak çalışır. Bir eşleşme bulunursa, istenen komut kimliği komut harita içeren uygulamaya bir WM_COMMAND ileti gönderilir. (Açıklamasına bakın `ON_OLECMD` aşağıda.) Bu şekilde, uygulamaya dağıtılan OLE komutları WM_COMMAND iletileri MFC tarafından açık olabilir. WM_COMMAND iletileri ardından MFC standardını kullanarak uygulamanın ileti eşlemeleri yönlendirilir [komut yönlendirme](../mfc/command-routing.md) mimarisi.

İleti eşlemeleri, MFC OLE komutu eşlemeleri ClassWizard tarafından desteklenmez. MFC geliştiriciler OLE komut eşleme desteği ve OLE komut eşleme girişleri el ile eklemeniz gerekir. Haritalar WM_COMMAND ileti yönlendirme zincirinde etkin belgeyi sırasında olan herhangi bir sınıf içinde MFC etkin belge sunucuları eklenebilir OLE yerinde etkin bir kapsayıcıdaki bir komuttur. Bu sınıflar türetilen uygulamanın sınıflarını [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md), ve [Coleıpframewnd](../mfc/reference/coleipframewnd-class.md). Etkin belge kapsayıcıları OLE komutu eşlemeleri yalnızca eklenebilir [Coledocobjectıtem](../mfc/reference/coledocobjectitem-class.md)-türetilmiş sınıf. Ayrıca, etkin belge kapsayıcıları WM_COMMAND iletileri yalnızca ileti eşlemede için dağıtılacağı `COleDocObjectItem`-türetilmiş sınıf.

## <a name="ole-command-map-macros"></a>OLE komut eşleme makroları

Sınıfınıza komut Haritası işlevini eklemek için aşağıdaki makroları kullanın:

```cpp
DECLARE_OLECMD_MAP ()
```

Bu makro sınıfı bildiriminde komut eşlemesini içeren sınıfın içinde (genelde üstbilgi dosyası) gider.

```cpp
BEGIN_OLECMD_MAP(theClass, baseClass)
```

*Sınıfın*<br/>
Komut eşlemesini içeren sınıfın adı.

*baseClass*<br/>
Komut eşlemesini içeren sınıfın temel sınıfının adı.

Bu makro, komut eşleme başına işaretler. Bu makro, komut eşlemesini içeren sınıf için uygulama dosyasında kullanın.

```
END_OLECMD_MAP()
```

Bu makro, komut harita sonunu işaretler. Bu makro, komut eşlemesini içeren sınıf için uygulama dosyasında kullanın. Bu makro, her zaman BEGIN_OLECMD_MAP makrosu izlemeniz gerekir.

```
ON_OLECMD(pguid, olecmdid, id)
```

*pguid*<br/>
OLE, komutun komut grubu GUID işaretçisi. Bu parametre **NULL** standart OLE komut grubu.

*olecmdid*<br/>
Çağrılacak komutun OLE komut kimliği.

*id*<br/>
Bu OLE komut çağrıldığında komut harita içeren uygulamaya gönderilecek WM_COMMAND ileti kimliği.

ON_OLECMD makrosu komut haritada kullanmak istediğiniz OLE komutları girdileri eklemek üzere kullanın. OLE komutlar alındığında, bunlar için belirtilen WM_COMMAND ileti dönüştürülür ve standart komut yönlendirmeyi MFC mimarisi kullanarak uygulamanın ileti eşlemesi üzerinden yönlendirilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, işlemeye için MFC etkin belge Sunucusu'nun OLE işleme komut özelliği eklemek gösterilmektedir [OLECMDID_PRINT](/windows/desktop/api/docobj/ne-docobj-olecmdid) OLE komutu. Bu örnekte AppWizard bir etkin belge sunucusu olan bir MFC uygulaması oluşturmak için kullandığınız varsayılır.

1. İçinde `CView`-türetilmiş sınıfın üstbilgi dosyasında, sınıf bildirimine DECLARE_OLECMD_MAP makro ekleyin.

    > [!NOTE]
    > Kullanım `CView`-WM_COMMAND ileti yönlendirme zincirinde etkin belge sunucusu sınıflarda biri olduğundan türetilmiş sınıf.

    ```cpp
    class CMyServerView : public CView
    {
    protected: // create from serialization only
        CMyServerView();
        DECLARE_DYNCREATE(CMyServerView)
        DECLARE_OLECMD_MAP()
        // . . .
    };
    ```

2. İçin uygulama dosyasında `CView`-türetilmiş sınıf, BEGIN_OLECMD_MAP ve END_OLECMD_MAP makroları ekleyin:

    ```cpp
    BEGIN_OLECMD_MAP(CMyServerView, CView)

    END_OLECMD_MAP()
    ```

3. Standart OLE yazdırma komutunu işlemek için ekleme bir [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) makrosu komut eşlemesine standart yazdırma komutu için OLE komut Kimliğini belirtme ve **ıd_fıle_prınt** WM_COMMAND kimliği için **Id_fıle_prınt** yazdırma komut kimliği MFC AppWizard tarafından oluşturulan uygulamalar tarafından kullanılan standart'tır:

    ```
    BEGIN_OLECMD_MAP(CMyServerView, CView)
        ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)
    END_OLECMD_MAP()
    ```

Afxdocob.h içinde tanımlı standart OLE komut makroları birini yerine ON_OLECMD makrosu kullanılamadı çünkü olduğunu unutmayın **OLECMDID_PRINT** standart bir OLE komut kimliği. On_olecmd_prınt makrosu, yukarıda gösterilen ON_OLECMD makrosu aynı görevi yerine getirmiş olacaksınız.

Bu sunucu gönderdiğinde kapsayıcılı bir uygulama bir **OLECMDID_PRINT** komutu ile sunucunun `IOleCommandTarget` arabirimi, komut işleyicisi yazdırma MFC Uygulama Yazdırma Sunucusu'nun neden Server'da çağrılacak. Yukarıdaki adımlarda eklenen yazdırma komutu çağırmak için etkin belgeyi kapsayıcının kodu şöyle görünür:

```cpp
void CContainerCntrItem::DoOleCmd()
{
    IOleCommandTarget *pCmd = NULL;
    HRESULT hr = E_FAIL;
    OLECMD ocm={OLECMDID_PRINT, 0};

    hr = m_lpObject->QueryInterface(
        IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));

    if (FAILED(hr))
        return;

    hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);

    if (SUCCEEDED(hr) && (ocm.cmdf& OLECMDF_ENABLED))
    {
        //Command is available and enabled so call it
        COleVariant vIn;
        COleVariant vOut;
        hr = pCmd->Exec(NULL, OLECMDID_PRINT,
            OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);
        ASSERT(SUCCEEDED(hr));
    }
    pCmd->Release();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
