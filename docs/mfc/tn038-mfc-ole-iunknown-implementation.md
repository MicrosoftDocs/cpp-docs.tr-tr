---
description: 'Daha fazla bilgi edinin: TN038: MFC/OLE IUnknown uygulama'
title: 'TN038: MFC-OLE IUnknown uygulama'
ms.date: 06/28/2018
helpviewer_keywords:
- aggregation macros [MFC]
- COM interfaces, base interface
- IUnknown interface
- END_INTERFACE_MAP macro [MFC]
- TN038
- BEGIN_INTERFACE_PART macro [MFC]
- DECLARE_INTERFACE_MAP macro [MFC]
- BEGIN_INTERFACE_MAP macro [MFC]
- OLE [MFC], implementing IUnknown interface
- METHOD_PROLOGUE macro [MFC]
- STDMETHOD macro [MFC]
- END_INTERFACE_PART macro [MFC]
- INTERFACE_PART macro
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
ms.openlocfilehash: 64a921fec560c375440f0430d4804aa78e533c6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215410"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038: MFC/OLE IUnknown Uygulaması

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

OLE 2 ' nin kalpde "OLE bileşen nesne modeli" veya COM. COM, birlikte çalışan nesnelerinin birbirleriyle nasıl iletişim kuracağını belirten bir standart tanımlar. Bu, yöntemlerin bir nesne üzerinde nasıl dağıtıldığı da dahil olmak üzere, "nesne" nin nasıl göründüğüne ilişkin ayrıntıları içerir. COM Ayrıca, tüm COM uyumlu sınıfların türetildiği bir temel sınıf tanımlar. Bu temel sınıf [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)'dir. [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimine bir C++ sınıfı denir, ancak com herhangi bir dile özgü değildir; C, Pascal veya bir com nesnesinin ikili yerleşimini destekleyebilen başka bir dilde uygulanabilir.

OLE, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'dan türetilmiş tüm sınıflara "arabirimler" olarak başvurur. [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) gibi bir "arabirim" bir uygulamayla birlikte bulunduğundan, bu önemli bir ayırım değildir. Yalnızca nesnelerin iletişim kurduğu protokolü tanımlar, bu uygulamaların ne yapabileceğine ilişkin ayrıntıları değildir. Bu, en yüksek esnekliğe izin veren bir sistem için uygun değildir. MFC/C++ programları için varsayılan bir davranış uygulayan MFC 'nin işi.

MFC 'nin [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygulanmasını anlamak için öncelikle bu arabirimin ne olduğunu anlamanız gerekir. [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'nin basitleştirilmiş bir sürümü aşağıda tanımlanmıştır:

```cpp
class IUnknown
{
public:
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;
    virtual ULONG AddRef() = 0;
    virtual ULONG Release() = 0;
};
```

> [!NOTE]
> Gibi bazı gerekli çağırma kuralı ayrıntıları, **`__stdcall`** Bu çizim için bırakılır.

[AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) üye işlevleri, nesnenin bellek yönetimini denetler. COM, nesneleri izlemek için bir başvuru sayım şeması kullanır. C++ ' da olduğu gibi, bir nesneye hiçbir şekilde doğrudan başvurulmuyor. Bunun yerine, COM nesnelerine her zaman bir işaretçi aracılığıyla başvurulur. Sahibi tarafından yapıldığında nesneyi serbest bırakmak için, nesnenin [yayın](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) üyesi çağırılır (bir geleneksel C++ nesnesi için yapıldığı gibi işleç silmeyi kullanmanın aksine). Başvuru sayma mekanizması, tek bir nesneye birden çok başvurunun yönetilmesine izin verir. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) uygulamaları nesnede bir başvuru sayısı tutar — nesne, başvuru sayısı sıfıra ulaşıncaya kadar silinmez.

[AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) bir uygulama açısından oldukça basittir. İşte basit bir uygulama:

```cpp
ULONG CMyObj::AddRef()
{
    return ++m_dwRef;
}

ULONG CMyObj::Release()
{
    if (--m_dwRef == 0)
    {
        delete this;
        return 0;
    }
    return m_dwRef;
}
```

[QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) üye işlevi biraz daha ilginç. Yalnızca üye işlevleri [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) olan bir nesnenin olması çok ilginç değildir. Bu, nesneye [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) tarafından sağlanan daha fazla şey olmasını söylemek iyi olabilir. Bu, [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) 'in yararlı olduğu yerdir. Aynı nesne üzerinde farklı bir "arabirim" elde etmenizi sağlar. Bu arabirimler genellikle [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'dan türetilir ve yeni üye işlevleri ekleyerek ek işlevsellik ekler. COM arabirimleri hiçbir şekilde arabirimde bildirilmemiş üye değişkenlerine sahip değildir ve tüm üye işlevleri saf-sanal olarak belirtilir. Örneğin,

```cpp
class IPrintInterface : public IUnknown
{
public:
    virtual void PrintObject() = 0;
};
```

Yalnızca bir [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)varsa bir IPrintInterface almak için, ' nı kullanarak [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) 'i çağırın `IID` `IPrintInterface` . , `IID` Arabirimi benzersiz bir şekilde tanımlayan 128 bitlik bir sayıdır. `IID`Sizin ya da OLE tarafından tanımladığınız her arabirim için bir vardır. *Punk* bir [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) nesnesine bir Işaretçisiyse, bundan bir IPrintInterface alma kodu şu olabilir:

```cpp
IPrintInterface* pPrint = NULL;
if (pUnk->QueryInterface(IID_IPrintInterface, (void**)&pPrint) == NOERROR)
{
    pPrint->PrintObject();
    pPrint->Release();
    // release pointer obtained via QueryInterface
}
```

Oldukça kolaydır, ancak bu durumda IPrintInterface ve [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimini destekleyen bir nesne nasıl uygulanır, çünkü IPrintInterface doğrudan [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'den türetiliyor çünkü IPrintInterface 'i uygulayarak [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) otomatik olarak desteklenir. Örneğin:

```cpp
class CPrintObj : public CPrintInterface
{
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
    virtual ULONG AddRef();
    virtual ULONG Release();
    virtual void PrintObject();
};
```

[AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) uygulamaları, yukarıda uygulananlarla tamamen aynı olacaktır. `CPrintObj::QueryInterface` Şuna benzer:

```cpp
HRESULT CPrintObj::QueryInterface(REFIID iid, void FAR* FAR* ppvObj)
{
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)
    {
        *ppvObj = this;
        AddRef();
        return NOERROR;
    }
    return E_NOINTERFACE;
}
```

Görebileceğiniz gibi, arabirim tanımlayıcısı (IID) tanınırsa, nesnenizin bir işaretçisi döndürülür; Aksi takdirde bir hata oluşur. Ayrıca, başarılı bir [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) 'In kapsanan [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)ile sonuçlandığına de göz önünde unutmayın. Kuşkusuz, CEditObj::P rint ' i de uygulamanız gerekir. Bu basit bir işlemdir çünkü IPrintInterface doğrudan [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabiriminden elde edilmiştir. Ancak, her ikisi de [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)'den türetilmiş iki farklı arabirimi desteklemek istiyorsanız aşağıdakileri göz önünde bulundurun:

```cpp
class IEditInterface : public IUnkown
{
public:
    virtual void EditObject() = 0;
};
```

C++ birden çok devralma de dahil olmak üzere hem ıeditınterface hem de IPrintInterface 'i destekleyen bir sınıf uygulamak için çeşitli farklı yollar olsa da, bu notta bu işlevselliği uygulamak için iç içe sınıfların kullanımı yoğunlaşacaktır.

```cpp
class CEditPrintObj
{
public:
    CEditPrintObj();

    HRESULT QueryInterface(REFIID iid, void**);
    ULONG AddRef();
    ULONG Release();
    DWORD m_dwRef;

    class CPrintObj : public IPrintInterface
    {
    public:
        CEditPrintObj* m_pParent;
        virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
        virtual ULONG AddRef();
        virtual ULONG Release();
    } m_printObj;

    class CEditObj : public IEditInterface
    {
    public:
        CEditPrintObj* m_pParent;
        virtual ULONG QueryInterface(REFIID iid, void** ppvObj);
        virtual ULONG AddRef();
        virtual ULONG Release();
    } m_editObj;
};
```

Uygulamanın tamamı aşağıda verilmiştir:

```cpp
CEditPrintObj::CEditPrintObj()
{
    m_editObj.m_pParent = this;
    m_printObj.m_pParent = this;
}

ULONG CEditPrintObj::AddRef()
{
    return ++m_dwRef;
}

CEditPrintObj::Release()
{
    if (--m_dwRef == 0)
    {
        delete this;
        return 0;
    }
    return m_dwRef;
}

HRESULT CEditPrintObj::QueryInterface(REFIID iid, void** ppvObj)
{
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)
    {
        *ppvObj = &m_printObj;
        AddRef();
        return NOERROR;
    }
    else if (iid == IID_IEditInterface)
    {
        *ppvObj = &m_editObj;
        AddRef();
        return NOERROR;
    }
    return E_NOINTERFACE;
}

ULONG CEditPrintObj::CEditObj::AddRef()
{
    return m_pParent->AddRef();
}

ULONG CEditPrintObj::CEditObj::Release()
{
    return m_pParent->Release();
}

HRESULT CEditPrintObj::CEditObj::QueryInterface(REFIID iid, void** ppvObj)
{
    return m_pParent->QueryInterface(iid, ppvObj);
}

ULONG CEditPrintObj::CPrintObj::AddRef()
{
    return m_pParent->AddRef();
}

ULONG CEditPrintObj::CPrintObj::Release()
{
    return m_pParent->Release();
}

HRESULT CEditPrintObj::CPrintObj::QueryInterface(REFIID iid, void** ppvObj)
{
    return m_pParent->QueryInterface(iid, ppvObj);
}
```

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygulamalarının çoğunun, CEditPrintObj:: CEditObj ve CEditPrintObj:: CPrintObj içindeki kodu çoğaltmak yerine CEditPrintObj sınıfına yerleştirildiğine dikkat edin. Bu, kod miktarını azaltır ve hataları önler. Buradaki anahtar nokta, IUnknown arabiriminden, nesne tarafından desteklenen herhangi bir arabirimi almak için [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) çağrısı yapılabilir ve bu arabirimlerin her birinden aynı şekilde yapılabilir. Bu, her arabirimdeki kullanılabilir tüm [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) işlevlerinin tam olarak aynı şekilde davranması gerektiği anlamına gelir. Bu katıştırılmış nesnelerin "dış nesne" içindeki uygulamayı çağırması için bir geri işaretçi kullanılır (m_pParent). M_pParent işaretçi CEditPrintObj Oluşturucusu sırasında başlatılır. Daha sonra CEditPrintObj:: CPrintObj::P rintObject ve CEditPrintObj:: CEditObj:: EditObject ' i de uygulamalısınız. Tek bir özellik eklemek için çok sayıda kod eklenmiştir — nesneyi düzenleme özelliği. Neyse ki, arabirimlerin yalnızca tek bir üye işlevi (gerçekleşse de) olması çok nadir bir durumdur ve bu durumda EditObject ve PrintObject genellikle tek bir arabirimde birleştirilir.

Bu, basit bir senaryo için çok fazla açıklama ve çok sayıda kod. MFC/OLE sınıfları daha basit bir alternatif sağlar. MFC Uygulama, Windows iletilerinin Ileti eşlemeleriyle Sarmalanma biçimine benzer bir teknik kullanır. Bu özellik, *arabirim haritaları* olarak adlandırılır ve sonraki bölümde açıklanmaktadır.

## <a name="mfc-interface-maps"></a>MFC Arabirim Eşlemeleri

MFC/OLE, kavram ve yürütme bölümünde MFC 'nin "Ileti eşlemeleri" ve "dağıtım haritaları" gibi "arabirim haritaları" uygulamasını içerir. MFC 'nin arabirim haritalarının temel özellikleri şunlardır:

- Sınıfında yerleşik olarak bulunan [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)standart bir uygulamasıdır `CCmdTarget` .

- Başvuru sayısının bakımı, [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) tarafından değiştirildi

- Veri odaklı [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) uygulama

Ayrıca, arabirim haritaları aşağıdaki gelişmiş özellikleri destekler:

- Toplanabilir COM nesneleri oluşturma desteği

- Bir COM nesnesi uygulamasında toplama nesnelerini kullanma desteği

- Uygulama sabitlenebilir ve Genişletilebilir

Toplama hakkında daha fazla bilgi için [toplama](/windows/win32/com/aggregation) konusuna bakın.

MFC 'nin arabirim eşleme desteğiyle sınıfında kök olarak yer verilir `CCmdTarget` . `CCmdTarget` "*a*" başvuru sayısı ve [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygulamasıyla ilişkili tüm üye işlevleri (örneğin, başvuru sayısı `CCmdTarget` ). OLE COM destekleyen bir sınıf oluşturmak için, ' dan bir sınıf türetirsiniz `CCmdTarget` ve `CCmdTarget` istenen arabirimleri uygulamak için üye işlevlerinin yanı sıra çeşitli makroları kullanırsınız. MFC 'nin uygulama, yukarıdaki örnekte olduğu gibi her arabirim uygulamasını tanımlamak için iç içe geçmiş sınıfları kullanır. Bu, bir IUnknown standart uygulamasıyla ve yinelenen kodların bazılarını ortadan kaldıran birçok makro ile daha kolay hale getirilir.

## <a name="interface-map-basics"></a>Arabirim eşlemesi temelleri

### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>MFC 'nin arabirim eşlemelerini kullanarak bir sınıf uygulamak için

1. Doğrudan ya da dolaylı olarak bir sınıf türet `CCmdTarget` .

2. `DECLARE_INTERFACE_MAP`Türetilmiş sınıf tanımındaki işlevini kullanın.

3. Desteklemek istediğiniz her arabirim için, sınıf tanımındaki BEGIN_INTERFACE_PART ve END_INTERFACE_PART makrolarını kullanın.

4. Uygulama dosyasında, sınıfın arabirim haritasını tanımlamak için BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP makrolarını kullanın.

5. Desteklenen her IID için, BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP makroları arasındaki INTERFACE_PART makrosunu kullanarak bu IID 'yi sınıfınızın belirli bir "bölümüne" eşleyin.

6. Desteklenen arabirimleri temsil eden iç içe sınıfların her birini uygulayın.

7. Üst,-türetilmiş nesneye erişmek için METHOD_PROLOGUE makrosunu kullanın `CCmdTarget` .

8. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) , `CCmdTarget` Bu işlevlerin uygulanmasını temsil edebilir ( `ExternalAddRef` , `ExternalRelease` ve `ExternalQueryInterface` ).

Yukarıdaki CPrintEditObj örneği aşağıdaki gibi uygulanabilir:

```cpp
class CPrintEditObj : public CCmdTarget
{
public:
    // member data and member functions for CPrintEditObj go here

// Interface Maps
protected:
    DECLARE_INTERFACE_MAP()

    BEGIN_INTERFACE_PART(EditObj, IEditInterface)
        STDMETHOD_(void, EditObject)();
    END_INTERFACE_PART(EditObj)

    BEGIN_INTERFACE_PART(PrintObj, IPrintInterface)
        STDMETHOD_(void, PrintObject)();
    END_INTERFACE_PART(PrintObj)
};
```

Yukarıdaki bildirim, öğesinden türetilmiş bir sınıf oluşturur `CCmdTarget` . DECLARE_INTERFACE_MAP makrosu, çerçeveye bu sınıfın özel arabirim eşlemesine sahip olacağını söyler. Ayrıca, BEGIN_INTERFACE_PART ve END_INTERFACE_PART makroları iç içe geçmiş sınıfları tanımlar, bu durumda CEditObj ve CPrintObj adlarıyla (X yalnızca "C" ile başlayan ve "I" ile başlayan arabirim sınıflarıyla iç içe yerleştirilmiş sınıfları ayırt etmek için kullanılır). Bu sınıfların iç içe geçmiş iki üyesi oluşturulur: sırasıyla m_CEditObj ve m_CPrintObj. Makrolar [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) işlevlerini otomatik olarak bildirir; Bu nedenle, yalnızca bu arabirime özgü işlevleri bildirmeniz gerekir: EditObject ve PrintObject (OLE makrosu STDYÖNTEMI, **_stdcall** ve sanal anahtar sözcüklerin hedef platforma uygun şekilde sağlanması için kullanılır).

Bu sınıfa ait arabirim eşlemesini uygulamak için:

```cpp
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)
END_INTERFACE_MAP()
```

Bu, IID_IPrintInterface IID 'yi m_CPrintObj ve IID_IEditInterface sırasıyla m_CEditObj ile bağlar. `CCmdTarget` [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) () uygulamasının uygulanması, `CCmdTarget::ExternalQueryInterface` Bu eşlemeyi m_CPrintObj ve istendiğinde m_CEditObj işaretçileri döndürecek şekilde kullanır. İçin bir giriş eklemek gerekli değildir `IID_IUnknown` ; çerçeve, haritada ilk arabirimi (Bu örnekte, m_CPrintObj) kullanır `IID_IUnknown` .

BEGIN_INTERFACE_PART makro sizin için [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) işlevlerini otomatik olarak bildirse de, bunları uygulamanız gerekir:

```cpp
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return pThis->ExternalAddRef();
}

ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return pThis->ExternalRelease();
}

HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(
    REFIID iid,
    void FAR* FAR* ppvObj)
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    return (HRESULT)pThis->ExternalQueryInterface(&iid, ppvObj);
}

void FAR EXPORT CEditPrintObj::XEditObj::EditObject()
{
    METHOD_PROLOGUE(CEditPrintObj, EditObj)
    // code to "Edit" the object, whatever that means...
}
```

CEditPrintObj:: CPrintObj için uygulama, CEditPrintObj:: CEditObj için yukarıdaki tanımlara benzer olacaktır. Bu işlevleri otomatik olarak oluşturmak için kullanılabilecek bir makro oluşturmak mümkün olsa da (daha önce MFC/OLE Geliştirme sürümünde bu durum büyük bir durumdur), bir makro birden fazla kod satırı oluşturduğunda kesme noktaları ayarlamak zordur. Bu nedenle, bu kod el ile genişletilir.

İleti eşlemelerinin çerçeve uygulamasını kullanarak, yapılması gereken birkaç şey vardır:

- QueryInterface uygulama

- AddRef ve Release Uygula

- Arabirimlerinizin her ikisinde de bu yerleşik yöntemlerin birini bildirin

Ayrıca Framework, dahili olarak ileti haritaları kullanır. Bu, `COleServerDoc` belirli arabirimleri zaten destekleyen ve Framework tarafından sağlanan arabirimlere değişiklik veya eklemeler sağlayan bir çerçeve sınıfından türetmeniz sağlar. Bu, Framework bir temel sınıftan arabirim haritasını devralmayı tam olarak desteklediği için yapabilirsiniz. Bunun nedeni, BEGIN_INTERFACE_MAP ikinci parametre olarak taban sınıfının adı kadar sürer.

> [!NOTE]
> MFC sürümünden söz konusu arabirimin gömülü özelleştirmesi devralınarak, MFC 'nin yerleşik uygulamalarının uygulamanın uygulama uygulamasının yerleşik uygulamalarını yeniden kullanmak mümkün değildir. Bu mümkün değildir çünkü içerilen türetilmiş nesneye erişim elde etmek için METHOD_PROLOGUE makrosunun kullanımı `CCmdTarget` , türetilmiş nesnenin gömülü nesnesinin *sabit bir sapmasını* ifade etmez `CCmdTarget` . Yani, örneğin, `COleClientItem::XAdviseSink` XAdviseSink nesnenin en üstünden belirli bir uzaklığa bağlı olduğundan, MFC 'nin uygulamasındaki uygulamasından ekli bir XMyAdviseSink türetilemez `COleClientItem` .

> [!NOTE]
> Ancak MFC 'nin varsayılan davranışını istediğiniz tüm işlevler için MFC uygulamasına temsilci atayabilirsiniz. Bu, `IOleInPlaceFrame` sınıfındaki (XOleInPlaceFrame) MFC uygulamasında yapılır `COleFrameHook` (birçok işlev için m_xOleInPlaceUIWindow temsilciler). Bu tasarım, birçok arabirimi uygulayan nesnelerin çalışma zamanı boyutunu azaltmak için seçilmiştir; bir arka işaretçi gereksinimini ortadan kaldırır (örneğin, önceki bölümde kullanılan m_pParent gibi).

### <a name="aggregation-and-interface-maps"></a>Toplama ve arabirim haritaları

Tek başına COM nesnelerinin desteklenmesinin yanı sıra, MFC Ayrıca toplamayı da destekler. Toplama işlemi, burada tartışmak için çok karmaşık bir konudur; toplama hakkında daha fazla bilgi için [toplama](/windows/win32/com/aggregation) konusuna bakın. Bu notta, Framework ve arabirim eşlemlerinde yerleşik olarak bulunan toplama desteği açıklanır.

Toplama kullanmanın iki yolu vardır: (1) toplamayı destekleyen bir COM nesnesi kullanarak ve (2) başka bir tarafından toplanabilecek bir nesne uygulama. Bu yetenekler "bir toplama nesnesi kullanma" ve "nesne toplanabilir hale getirme" olarak adlandırılabilir. MFC her ikisini de destekler.

### <a name="using-an-aggregate-object"></a>Toplama nesnesi kullanma

Bir toplama nesnesi kullanmak için, toplama yöntemini bir araya getirmek için bir yol olması gerekir. Diğer bir deyişle, toplama nesnesi, nesnenizin yerel bir parçası olsa da gibi davranmalıdır. Bu nedenle, iç içe geçmiş bir nesnenin IID ile eşlendiği INTERFACE_PART makroya ek olarak MFC 'nin arabirim eşleme mekanizmasına nasıl bir araya geçildiği, türetilmiş sınıfınızın bir parçası olarak bir toplama nesnesi de bildirebilirsiniz `CCmdTarget` . Bunu yapmak için INTERFACE_AGGREGATE makrosu kullanılır. Bu, arabirim eşleme mekanizmasına tümleştirilecek bir üye değişkeni ( [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) veya türetilmiş bir sınıfa yönelik bir işaretçi olması gerekir) belirtmenize olanak tanır. Çağrıldığında işaretçi NULL değilse `CCmdTarget::ExternalQueryInterface` , istenen nesnenin [](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) `IID` `IID` kendisi tarafından desteklenen yerel öğeleri yoksa, çerçeve otomatik olarak toplama nesnesinin QueryInterface üye işlevini çağırır `CCmdTarget` .

#### <a name="to-use-the-interface_aggregate-macro"></a>INTERFACE_AGGREGATE makrosunu kullanmak için

1. `IUnknown*`Toplam nesnesine bir işaretçi içeren bir üye değişkeni (a) bildirin.

2. Ad ile üye değişkenine başvuran arabirim haritanızda bir INTERFACE_AGGREGATE makrosu ekleyin.

3. Bir noktada (genellikle sırasında `CCmdTarget::OnCreateAggregates` ), üye DEĞIŞKENINI null dışında bir şeye başlatın.

Örneğin:

```cpp
class CAggrExample : public CCmdTarget
{
public:
    CAggrExample();

protected:
    LPUNKNOWN m_lpAggrInner;
    virtual BOOL OnCreateAggregates();

    DECLARE_INTERFACE_MAP()
    // "native" interface part macros may be used here
};

CAggrExample::CAggrExample()
{
    m_lpAggrInner = NULL;
}

BOOL CAggrExample::OnCreateAggregates()
{
    // wire up aggregate with correct controlling unknown
    m_lpAggrInner = CoCreateInstance(CLSID_Example,
        GetControllingUnknown(), CLSCTX_INPROC_SERVER,
        IID_IUnknown, (LPVOID*)&m_lpAggrInner);

    if (m_lpAggrInner == NULL)
        return FALSE;
    // optionally, create other aggregate objects here
    return TRUE;
}

BEGIN_INTERFACE_MAP(CAggrExample, CCmdTarget)
    // native "INTERFACE_PART" entries go here
    INTERFACE_AGGREGATE(CAggrExample, m_lpAggrInner)
END_INTERFACE_MAP()
```

M_lpAggrInner değişkeni oluşturucuda NULL olarak başlatılır. Çerçeve, varsayılan [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))UYGULAMASıNDA bir null üye değişkenini yoksayar. `OnCreateAggregates` Aslında toplama nesnelerinizi oluşturmak için iyi bir yerdir. Nesneyi MFC uygulamasının dışında oluşturuyorsanız, bunu açıkça çağırmanız gerekir `COleObjectFactory` . ' De toplama oluşturma nedeni ve ' `CCmdTarget::OnCreateAggregates` nin kullanımı, `CCmdTarget::GetControllingUnknown` toplanılan nesneleri oluştururken görünür hale gelir.

Bu teknik, nesnenizin toplama nesnesinin desteklediği tüm arabirimlerin yanı sıra kendi yerel arabirimlerini sağlayacaktır. Yalnızca toplamanın desteklediği arabirimlerin bir alt kümesini isterseniz, geçersiz kılabilirsiniz `CCmdTarget::GetInterfaceHook` . Bu, [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))'e benzer bir çok düşük düzey hookability sağlar. Genellikle, toplamanın desteklediği tüm arabirimlerin olmasını istersiniz.

### <a name="making-an-object-implementation-aggregatable"></a>Bir nesne uygulamasını toplanabilir hale getirme

Bir nesnenin toplanabilir olması için [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) uygulamasının bir "denetleme bilinmiyor" ile temsilci seçme gerekir. Diğer bir deyişle, nesnenin bir parçası olması için [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) 'i aynı zamanda [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)'ten türeten farklı bir nesneye vermelidir. Bu "denetimi bilinmiyor", oluşturulduğunda nesnesine sağlanır, diğer bir deyişle, uygulamasının uygulamasına sağlanır `COleObjectFactory` . Bunu uygulamak, az miktarda yük taşır ve bazı durumlarda istenen değildir, bu nedenle MFC bunu isteğe bağlı hale getirir. Bir nesnenin toplanabilir olmasını sağlamak için `CCmdTarget::EnableAggregation` nesnenin yapıcısını çağırın.

Nesne ayrıca toplamalar kullanıyorsa, doğru "denetimi bilinmiyor" öğesini de toplam nesnelere iletdiğinizden emin olmanız gerekir. Toplama oluşturulduğunda genellikle bu [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) işaretçisi nesnesine geçirilir. Örneğin, pUnkOuter parametresi ile oluşturulan nesneler için "bilinmeyen denetim" dir `CoCreateInstance` . Doğru "Denetim bilinmiyor" işaretçisi çağırarak elde edilebilir `CCmdTarget::GetControllingUnknown` . Ancak, bu işlevden döndürülen değer, Oluşturucu sırasında geçerli değildir. Bu nedenle, toplamanızı yalnızca bir geçersiz kılmada oluşturmanız önerilir `CCmdTarget::OnCreateAggregates` , burada dönüş değeri uygulamadan `GetControllingUnknown` oluşturulmuş olsa bile güvenilir `COleObjectFactory` .

Ayrıca, yapay başvuru sayılarını eklerken veya serbest bırakırken nesnenin doğru başvuru sayısını işlemesinin önemli olması da önemlidir. Bunun durumu olduğundan emin olmak için, ve yerine her zaman çağırın `ExternalAddRef` `ExternalRelease` `InternalRelease` `InternalAddRef` . `InternalRelease` `InternalAddRef` Toplamayı destekleyen bir sınıf üzerinde veya çağırmak nadir olarak belirlenir.

## <a name="reference-material"></a>Başvuru malzemeleri

Kendi arabirimlerinizi tanımlama veya Framework 'ün OLE arabirimlerinin uygulanmasını geçersiz kılma gibi OLE 'nin gelişmiş kullanımı, temel alınan arabirim eşleme mekanizmasının kullanımını gerektirir.

Bu bölümde, bu gelişmiş özellikleri uygulamak için kullanılan her makro ve API 'Ler açıklanmaktadır.

### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget:: Enabletoplamasını — Işlev açıklaması

```cpp
void EnableAggregation();
```

#### <a name="remarks"></a>Açıklamalar

Bu türden nesneler için OLE toplamayı desteklemek istiyorsanız türetilmiş sınıfın oluşturucusunda bu işlevi çağırın. Bu, toplanabilir nesneler için gerekli özel bir IUnknown uygulamasını hazırlar.

### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget:: ExternalQueryInterface — Işlev açıklaması

```cpp
DWORD ExternalQueryInterface(
    const void FAR* lpIID,
    LPVOIDFAR* ppvObj
);
```

#### <a name="parameters"></a>Parametreler

*Lpiıd*<br/>
Bir IID 'ye yönelik bir işaretçi (QueryInterface 'e ilk bağımsız değişken)

*ppvObj*<br/>
IUnknown * işaretçisi (QueryInterface için ikinci bağımsız değişken)

#### <a name="remarks"></a>Açıklamalar

Sınıfınızın uyguladığı her arabirim için IUnknown uygulamanızda bu işlevi çağırın. Bu işlev, nesnenizin arabirim eşlemesine dayalı olarak QueryInterface 'in standart veri odaklı uygulamasını sağlar. Dönüş değerinin HRESULT değerine dönüştürülmesi gerekir. Nesne toplanırsa, bu işlev yerel arabirim eşlemesini kullanmak yerine "IUnknown denetimi" ni çağırır.

### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget:: ExternalAddRef — Işlev açıklaması

```cpp
DWORD ExternalAddRef();
```

#### <a name="remarks"></a>Açıklamalar

Sınıfınızın uyguladığı her arabirim için IUnknown:: AddRef uygulamanızda bu işlevi çağırın. Dönüş değeri, CCmdTarget nesnesindeki yeni başvuru sayısıdır. Nesne toplanırsa, bu işlev yerel başvuru sayısını değiştirmek yerine "IUnknown denetimi" ni çağırır.

### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget:: ExternalRelease — Işlev açıklaması

```cpp
DWORD ExternalRelease();
```

#### <a name="remarks"></a>Açıklamalar

Sınıfınızın uyguladığı her arabirim için IUnknown:: Release uygulamanızda bu işlevi çağırın. Dönüş değeri, nesnedeki yeni başvuru sayısını gösterir. Nesne toplanırsa, bu işlev yerel başvuru sayısını değiştirmek yerine "IUnknown denetimi" ni çağırır.

### <a name="declare_interface_map--macro-description"></a>DECLARE_INTERFACE_MAP — makro açıklaması

```cpp
DECLARE_INTERFACE_MAP
```

#### <a name="remarks"></a>Açıklamalar

Bu makroyu, `CCmdTarget` bir arabirim eşlemesine sahip olan sınıfından türetilmiş herhangi bir sınıfta kullanın. DECLARE_MESSAGE_MAP benzer şekilde kullanılır. Bu makro çağrısı, genellikle bir üst bilgide (. H) dosyası. DECLARE_INTERFACE_MAP olan bir sınıf, uygulama dosyasında arabirim eşlemesini tanımlamalıdır (. CPP) BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP makroları.

### <a name="begin_interface_part-and-end_interface_part--macro-descriptions"></a>BEGIN_INTERFACE_PART ve END_INTERFACE_PART — makro açıklamaları

```cpp
BEGIN_INTERFACE_PART(localClass, iface);
END_INTERFACE_PART(localClass)
```

#### <a name="parameters"></a>Parametreler

*localClass*<br/>
Arabirimi uygulayan sınıfın adı

*IACE*<br/>
Bu sınıfın uyguladığı arabirimin adı

#### <a name="remarks"></a>Açıklamalar

Sınıfınızın uygulayabileceği her arabirim için bir BEGIN_INTERFACE_PART ve END_INTERFACE_PART çiftiniz olması gerekir. Bu makrolar, tanımladığınız OLE arabiriminden ve bu sınıfın gömülü üye değişkenine türetilmiş bir yerel sınıf tanımlar. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) üyeleri otomatik olarak bildirilmiştir. Uygulanan arabirimin parçası olan diğer üye işlevleri için bildirimleri dahil etmeniz gerekir (Bu bildirimler BEGIN_INTERFACE_PART ve END_INTERFACE_PART makroları arasında yerleştirilir).

*İface* bağımsız değişkeni `IAdviseSink` , veya `IPersistStorage` (veya kendi özel arabiriminiz) gibi uygulamak istediğiniz OLE arabirimidir.

*LocalClass* bağımsız değişkeni, tanımlanacaktır yerel sınıfın adıdır. Ada bir ' X ' otomatik olarak eklenecek. Bu adlandırma kuralı, aynı ada sahip genel sınıflarla çakışmaları önlemek için kullanılır. Ayrıca, gömülü üyenin adı, ' m_x ' tarafından ön eki hariç *localClass* adıyla aynıdır.

Örneğin:

```cpp
BEGIN_INTERFACE_PART(MyAdviseSink, IAdviseSink)
    STDMETHOD_(void, OnDataChange)(LPFORMATETC, LPSTGMEDIUM);
    STDMETHOD_(void, OnViewChange)(DWORD, LONG);
    STDMETHOD_(void, OnRename)(LPMONIKER);
    STDMETHOD_(void, OnSave)();
    STDMETHOD_(void, OnClose)();
END_INTERFACE_PART(MyAdviseSink)
```

, ıvsesink öğesinden türetilen XMyAdviseSink adlı bir yerel sınıf ve m_xMyAdviseSink olarak bildirildiği sınıfın bir üyesini tanımlar. Note:

> [!NOTE]
> _ İle başlayan satırlar `STDMETHOD` aslında OLE2 öğesinden kopyalanır. H ve biraz daha değiştirildi. OLE2 adresinden kopyalanıyor. H, çözülmesi zor olan hataları azaltabilir.

### <a name="begin_interface_map-and-end_interface_map--macro-descriptions"></a>BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP — makro açıklamaları

```cpp
BEGIN_INTERFACE_MAP(theClass, baseClass)
END_INTERFACE_MAP
```

#### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Arabirim eşlemesinin tanımlanması gereken sınıf

*baseClass*<br/>
Sınıfı 'ın türetildiği  sınıf.

#### <a name="remarks"></a>Açıklamalar

BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP makroları, arabirim eşlemesini gerçekten tanımlamak için uygulama dosyasında kullanılır. Uygulanan her arabirim için bir veya daha fazla makro çağırma INTERFACE_PART. Sınıfın kullandığı her bir toplama için bir INTERFACE_AGGREGATE makro çağrısı vardır.

### <a name="interface_part--macro-description"></a>INTERFACE_PART — makro açıklaması

```cpp
INTERFACE_PART(theClass, iid, localClass)
```

#### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Arabirim eşlemesini içeren sınıfın adı.

*'si*<br/>
`IID`Katıştırılmış sınıfa eşlenecek.

*localClass*<br/>
Yerel sınıfın adı (' X ' daha az).

#### <a name="remarks"></a>Açıklamalar

Bu makro, nesnenizin destekleyeceği her arabirim için BEGIN_INTERFACE_MAP makrosu ve END_INTERFACE_MAP makrosu arasında kullanılır. Bir IID *'yi, sınıfsınıfı ve* *localClass* tarafından belirtilen sınıfın bir üyesine eşlemenizi sağlar. ' M_x ', *localClass* 'a otomatik olarak eklenecektir. Birden fazla `IID` üyenin tek bir üyeyle ilişkili olabileceğini unutmayın. Yalnızca bir "en çok türetilmiş" arabirimi uyguladığınızda ve tüm ara arabirimleri sağlamak istediğinizde bu çok yararlı olur. Bu arabirimin iyi bir örneğidir `IOleInPlaceFrameWindow` . Hiyerarşisi şuna benzer:

```Hierarchy
IUnknown
    IOleWindow
        IOleUIWindow
            IOleInPlaceFrameWindow
```

Bir nesne uygularsa `IOleInPlaceFrameWindow` , `QueryInterface` `IOleUIWindow` "en türetilmiş" arabiriminin yanı sıra, bir istemci şu arabirimlerin herhangi birinde olabilir:, `IOleWindow` veya [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) `IOleInPlaceFrameWindow` (aslında sizin uyguladıysanız). Bunu işlemek için birden fazla INTERFACE_PART makrosunu kullanarak her bir temel arabirimi `IOleInPlaceFrameWindow` arabirime eşleyin:

sınıf tanımı dosyasında:

```cpp
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)
```

sınıf uygulama dosyasında:

```cpp
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)
END_INTERFACE_MAP
```

Her zaman gerekli olduğundan, çerçeve IUnknown 'yi alır.

### <a name="interface_part--macro-description"></a>INTERFACE_PART — makro açıklaması

```cpp
INTERFACE_AGGREGATE(theClass, theAggr)
```

#### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Arabirim eşlemesini içeren sınıfın adı,

*ınggr*<br/>
Toplanacak üye değişkeninin adı.

#### <a name="remarks"></a>Açıklamalar

Bu makro, çerçeveye sınıfın bir toplama nesnesi kullandığını bildirmek için kullanılır. BEGIN_INTERFACE_PART ve END_INTERFACE_PART makroları arasında görünmesi gerekir. Toplama nesnesi, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)öğesinden türetilen ayrı bir nesnedir. Bir toplama ve INTERFACE_AGGREGATE makrosunu kullanarak, toplamanın desteklediği tüm arabirimlerin nesne tarafından doğrudan desteklendiğinden görünmesini sağlayabilirsiniz. IBU *bağımsız değişken, yalnızca* [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'dan türetilmiş (doğrudan veya dolaylı olarak) sınıfınızın üye değişkeninin adıdır. Tüm INTERFACE_AGGREGATE makroları, bir arabirim eşlemesine yerleştirildiğinde INTERFACE_PART makrolarının izlenmesi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
