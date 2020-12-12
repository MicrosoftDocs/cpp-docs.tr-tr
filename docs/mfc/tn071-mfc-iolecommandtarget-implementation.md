---
description: 'Daha fazla bilgi edinin: TN071: MFC IOleCommandTarget uygulama'
title: 'TN071: MFC IOleCommandTarget Uygulaması'
ms.date: 06/28/2018
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
ms.openlocfilehash: 190dd64f6fd14d6231a6870bf6697a9a85182166
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214513"
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: MFC IOleCommandTarget Uygulaması

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

`IOleCommandTarget`Arabirim, nesnelerin ve kapsayıcılarının birbirlerine komut gönderme yapmasına olanak sağlar. Örneğin, bir nesnenin araç çubukları,,, ve gibi komutlar için düğmeler `Print` içerebilir `Print Preview` `Save` `New` `Zoom` . Bu tür bir nesne, destekleyen bir kapsayıcıya katıştırılmışsa `IOleCommandTarget` , nesne düğmeleri etkinleştirebilir ve Kullanıcı tıkladıklarında, işlemek için komutları kapsayıcıya iletebilir. Bir kapsayıcı katıştırılmış nesnenin kendisini yazdırmasını istiyorlarsa, bu isteği katıştırılmış nesnenin arabirimi aracılığıyla bir komut göndererek yapabilir `IOleCommandTarget` .

`IOleCommandTarget` , bir istemci tarafından bir sunucuda yöntemleri çağırmak için kullanılan Otomasyon benzeri bir arabirimdir. Bununla birlikte, kullanmak `IOleCommandTarget` Otomasyon arabirimleri aracılığıyla çağrı yapma yükünü kaydeder çünkü programcılar genellikle pahalı olan yöntemini kullanmak zorunda değildir `Invoke` `IDispatch` .

MFC 'de arabirim, etkin belge `IOleCommandTarget` kapsayıcılarının sunucuya komut gönderme yapmasına izin vermek Için etkin belge sunucuları tarafından kullanılır. Etkin belge sunucusu sınıfı, `CDocObjectServerItem` arabirimi uygulamak IÇIN MFC Arabirim eşlemelerini (bkz. [TN038: MFC/OLE IUnknown uygulaması](../mfc/tn038-mfc-ole-iunknown-implementation.md)) kullanır `IOleCommandTarget` .

`IOleCommandTarget` , sınıfında de uygulanır `COleFrameHook` . `COleFrameHook` , yerinde düzenlenen kapsayıcının çerçeve penceresi işlevselliğini uygulayan belgelenmemiş bir MFC sınıfıdır. `COleFrameHook` Ayrıca, arabirimi uygulamak için MFC Arabirim eşlemelerini kullanır `IOleCommandTarget` . `COleFrameHook`uygulamasının, `IOleCommandTarget` OLE komutlarının `COleDocObjectItem` türemiş etkin belge kapsayıcılarını iletmesi. Bu, herhangi bir MFC etkin belge kapsayıcısının kapsanan etkin belge sunucularından ileti almasına izin verir.

## <a name="mfc-ole-command-maps"></a>MFC OLE komut eşlemeleri

MFC geliştiricileri, `IOleCommandTarget` MFC OLE komut haritalarını kullanarak avantajlarından yararlanabilir. OLE komut eşlemeleri ileti haritaları gibidir Çünkü OLE komutlarını komut eşlemesini içeren sınıfın üye işlevlerine eşlemek için kullanılabilirler. Bu işi yapmak için, işlemek istediğiniz komutun OLE komut grubunu, OLE komutunu ve OLE komutu alındığında gönderilecek [WM_COMMAND](/windows/win32/menurc/wm-command) ILETISININ komut kimliğini belirtmek için komut eşlemesine makrolar koyun. MFC ayrıca standart OLE komutları için bir dizi önceden tanımlanmış makro sağlar. Başlangıçta Microsoft Office uygulamalarla kullanılmak üzere tasarlanan standart OLE komutlarının bir listesi için, docobj. h içinde tanımlanan OLECMDıD numaralandırması bölümüne bakın.

Ole komutu eşleme içeren bir MFC uygulaması tarafından bir OLE komutu alındığında, MFC, uygulamanın OLE komut eşlemesindeki istenen komut için komut KIMLIĞINI ve komut grubunu bulmaya çalışır. Bir eşleşme bulunursa, istenen komutun KIMLIĞIYLE birlikte komut haritasını içeren uygulamaya bir WM_COMMAND iletisi gönderilir. (Aşağıdaki açıklamasına bakın `ON_OLECMD` .) Bu şekilde, bir uygulamaya dağıtılan OLE komutları MFC tarafından WM_COMMAND iletiler olarak açılır. WM_COMMAND iletileri daha sonra MFC standart [komut yönlendirme](../mfc/command-routing.md) mimarisi kullanılarak uygulamanın ileti haritaları aracılığıyla yönlendirilir.

İleti eşlemlerinin aksine, MFC OLE komut eşlemeleri ClassWizard tarafından desteklenmez. MFC geliştiricilerinin OLE komut Haritası desteği ve OLE komut eşleme girdilerini el ile eklemesi gerekir. OLE komut eşlemeleri, etkin belgenin yerinde etkin olduğu zaman, WM_COMMAND ileti-yönlendirme zincirindeki herhangi bir sınıftaki MFC etkin belge sunucularına eklenebilir. Bu sınıflar, [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md)ve [cotaipframewnd](../mfc/reference/coleipframewnd-class.md)'den türetilmiş uygulamanın sınıflarını içerir. Etkin belge kapsayıcılarında OLE komut eşlemeleri yalnızca [Cotadocobjectıtem](../mfc/reference/coledocobjectitem-class.md)-Derived sınıfına eklenebilir. Ayrıca, etkin belge kapsayıcılarında, WM_COMMAND iletileri yalnızca türetilmiş sınıftaki ileti eşlemesine gönderilir `COleDocObjectItem` .

## <a name="ole-command-map-macros"></a>OLE komut eşleme makroları

Sınıfınıza komut eşleme işlevselliği eklemek için aşağıdaki makroları kullanın:

```cpp
DECLARE_OLECMD_MAP ()
```

Bu makro, komut eşlemesini içeren sınıfın sınıf bildirimine (genellikle başlık dosyasında) gider.

```cpp
BEGIN_OLECMD_MAP(theClass, baseClass)
```

*Sınıf*<br/>
Komut eşlemesini içeren sınıfın adı.

*baseClass*<br/>
Komut eşlemesini içeren sınıfın temel sınıfının adı.

Bu makro, komut haritasının başlangıcını işaretler. Komut eşlemesini içeren sınıf için uygulama dosyasında bu makroyu kullanın.

```
END_OLECMD_MAP()
```

Bu makro, komut haritasının sonunu işaretler. Komut eşlemesini içeren sınıf için uygulama dosyasında bu makroyu kullanın. Bu makronun her zaman BEGIN_OLECMD_MAP makrosunu izlemesi gerekir.

```
ON_OLECMD(pguid, olecmdid, id)
```

*PGUID*<br/>
OLE komutunun komut grubunun GUID 'sine yönelik işaretçi. Bu parametre standart OLE komut grubu için **null** .

*OLECMDID*<br/>
Çağrılacak komutun OLE komut KIMLIĞI.

*id*<br/>
Bu OLE komutu çağrıldığında komut eşlemesini içeren uygulamaya gönderilecek WM_COMMAND iletisinin KIMLIĞI.

İşlemek istediğiniz OLE komutlarının girişlerini eklemek için komut eşlemesindeki ON_OLECMD makrosunu kullanın. OLE komutları alındığında, bu iletiler belirtilen WM_COMMAND iletisine dönüştürülür ve standart MFC komut yönlendirme mimarisi kullanılarak uygulamanın ileti eşlemesi aracılığıyla yönlendirilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, [OLECMDID_PRINT](/windows/win32/api/docobj/ne-docobj-olecmdid) OLE komutunu işlemek IÇIN bir MFC etkin belge sunucusuna OLE komut işleme özelliğinin nasıl ekleneceğini gösterir. Bu örnekte, etkin bir belge sunucusu olan bir MFC uygulaması oluşturmak için AppWizard 'ı kullandınız varsayılmaktadır.

1. `CView`Türetilmiş sınıfınızın başlık dosyasında, sınıf bildirimine DECLARE_OLECMD_MAP makrosunu ekleyin.

    > [!NOTE]
    > `CView`WM_COMMAND ileti yönlendirme zincirindeki etkin belge sunucusundaki sınıflardan biri olduğundan,-Derived sınıfını kullanın.

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

2. `CView`Türetilmiş sınıfın uygulama dosyasında BEGIN_OLECMD_MAP ve END_OLECMD_MAP makrolarını ekleyin:

    ```cpp
    BEGIN_OLECMD_MAP(CMyServerView, CView)

    END_OLECMD_MAP()
    ```

3. Standart OLE Print komutunu işlemek için, standart Yazdır komutu **ID_FILE_PRINT** ve WM_COMMAND KIMLIĞI için OLE komut kimliğini belirten komut eşlemesine bir [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) makrosu ekleyin. **ID_FILE_PRINT** , AppWizard tarafından oluşturulan mfc uygulamaları tarafından kullanılan standart yazdırma komutu kimliğidir:

    ```
    BEGIN_OLECMD_MAP(CMyServerView, CView)
        ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)
    END_OLECMD_MAP()
    ```

**OLECMDID_PRINT** standart OLE komut kimliği olduğundan, Afxdocob. h içinde tanımlanan standart ole komutu makrolarından birinin ON_OLECMD makro yerine kullanılabileceğini unutmayın. ON_OLECMD_PRINT makro yukarıda gösterilen ON_OLECMD makrodakiyle aynı görevi yerine getirmeyecektir.

Bir kapsayıcı uygulaması bu sunucuyu sunucu arabirimi aracılığıyla bir **OLECMDID_PRINT** komutu GÖNDERDIĞINDE `IOleCommandTarget` , MFC yazdırma komut işleyicisi sunucuda çağrılır ve bu da sunucunun uygulamayı yazdırmasına neden olur. Yukarıdaki adımlarda eklenen Print komutunu çağırmak için etkin belge kapsayıcısının kodu şuna benzer şekilde görünür:

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

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
