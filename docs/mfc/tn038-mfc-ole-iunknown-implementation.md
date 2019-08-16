---
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
ms.openlocfilehash: fb5ddf7fbbf2b59a8e0434e4b097284e309c918d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511057"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038: MFC/OLE IUnknown uygulama

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

OLE 2 ' nin kalpde "OLE bileşen nesne modeli" veya COM. COM, birlikte çalışan nesnelerinin birbirleriyle nasıl iletişim kuracağını belirten bir standart tanımlar. Bu, yöntemlerin bir nesne üzerinde nasıl dağıtıldığı da dahil olmak üzere, "nesne" nin nasıl göründüğüne ilişkin ayrıntıları içerir. COM Ayrıca, tüm COM uyumlu sınıfların türetildiği bir temel sınıf tanımlar. Bu temel sınıf [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)'dir. [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimine bir C++ sınıf olarak bahsedilse de com herhangi bir dile özgü DEĞILDIR; C, Pascal veya bir com nesnesinin ikili yerleşimini destekleyebilen başka bir dilde uygulanabilir.

OLE, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'dan türetilmiş tüm sınıflara "arabirimler" olarak başvurur. [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) gibi bir "arabirim" bir uygulamayla birlikte bulunduğundan, bu önemli bir ayırım değildir. Yalnızca nesnelerin iletişim kurduğu protokolü tanımlar, bu uygulamaların ne yapabileceğine ilişkin ayrıntıları değildir. Bu, en yüksek esnekliğe izin veren bir sistem için uygun değildir. MFC/C++ programlar için varsayılan bir davranış uygulayan MFC 'nin işi.

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
> Gibi bazı gerekli çağırma kuralı ayrıntıları, `__stdcall` bu çizim için bırakılır.

[AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) üye işlevleri, nesnenin bellek yönetimini denetler. COM, nesneleri izlemek için bir başvuru sayım şeması kullanır. Nesneye hiçbir şekilde doğrudan başvurmuş gibi başvurulmuyor C++. Bunun yerine, COM nesnelerine her zaman bir işaretçi aracılığıyla başvurulur. Sahibi ile işiniz bittiğinde nesneyi serbest bırakmak için, nesnenin [yayın](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) üyesi çağrılır (geleneksel C++ bir nesne için yapıldığı gibi işleç silmeyi kullanmanın aksine). Başvuru sayma mekanizması, tek bir nesneye birden çok başvurunun yönetilmesine izin verir. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) uygulamaları nesnede bir başvuru sayısı tutar — nesne, başvuru sayısı sıfıra ulaşıncaya kadar silinmez.

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

[QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) üye işlevi biraz daha ilginç. Yalnızca üye işlevleri [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) olan bir nesnenin olması çok ilginç değildir. Bu, nesneye [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) tarafından sağlanan daha fazla şey olmasını söylemek iyi olabilir. Bu, [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 'in yararlı olduğu yerdir. Aynı nesne üzerinde farklı bir "arabirim" elde etmenizi sağlar. Bu arabirimler genellikle [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'dan türetilir ve yeni üye işlevleri ekleyerek ek işlevsellik ekler. COM arabirimleri hiçbir şekilde arabirimde bildirilmemiş üye değişkenlerine sahip değildir ve tüm üye işlevleri saf-sanal olarak belirtilir. Örneğin,

```cpp
class IPrintInterface : public IUnknown
{
public:
    virtual void PrintObject() = 0;
};
```

Yalnızca bir [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)varsa bir IPrintInterface almak için, ' nı kullanarak [](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) `IID` `IPrintInterface`QueryInterface 'i çağırın. `IID` , Arabirimi benzersiz bir şekilde tanımlayan 128 bitlik bir sayıdır. Sizin ya da `IID` OLE tarafından tanımladığınız her arabirim için bir vardır. *Punk* bir [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) nesnesine bir Işaretçisiyse, bundan bir IPrintInterface alma kodu şu olabilir:

```cpp
IPrintInterface* pPrint = NULL;
if (pUnk->QueryInterface(IID_IPrintInterface, (void**)&pPrint) == NOERROR)
{
    pPrint->PrintObject();
    pPrint->Release();
    // release pointer obtained via QueryInterface
}
```

Bu oldukça kolay görünüyor, ancak bu durumda IPrintInterface ve [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimini destekleyen bir nesneyi, IPrintInterface ' i uygulayarak doğrudan [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'den türetildiğinden basit hale gelir. [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) otomatik olarak desteklenir. Örneğin:

```cpp
class CPrintObj : public CPrintInterface
{
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
    virtual ULONG AddRef();
    virtual ULONG Release();
    virtual void PrintObject();
};
```

[AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) uygulamaları, yukarıda uygulananlarla tamamen aynı olacaktır. `CPrintObj::QueryInterface`Şuna benzer:

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

Görebileceğiniz gibi, arabirim tanımlayıcısı (IID) tanınırsa, nesnenizin bir işaretçisi döndürülür; Aksi takdirde bir hata oluşur. Ayrıca, başarılı bir [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 'In kapsanan [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)ile sonuçlandığına de göz önünde unutmayın. Kuşkusuz, CEditObj::P rint ' i de uygulamanız gerekir. Bu basit bir işlemdir çünkü IPrintInterface doğrudan [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabiriminden elde edilmiştir. Ancak, her ikisi de [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)'den türetilmiş iki farklı arabirimi desteklemek istiyorsanız aşağıdakileri göz önünde bulundurun:

```cpp
class IEditInterface : public IUnkown
{
public:
    virtual void EditObject() = 0;
};
```

C++ Birden çok devralma da dahil olmak üzere hem ıeditınterface hem de IPrintInterface 'i destekleyen bir sınıf uygulamak için birçok farklı yol olsa da, bu notta bu işlevselliği uygulamak için iç içe sınıfların kullanımına odaklanacaktır.

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

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygulamalarının çoğunun, CEditPrintObj:: CEditObj ve CEditPrintObj:: CPrintObj içindeki kodu çoğaltmak yerine CEditPrintObj sınıfına yerleştirildiğine dikkat edin. Bu, kod miktarını azaltır ve hataları önler. Buradaki anahtar nokta, IUnknown arabiriminden, nesne tarafından desteklenen herhangi bir arabirimi almak için [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) çağrısı yapılabilir ve bu arabirimlerin her birinden aynı şekilde yapılabilir. Bu, her arabirimdeki kullanılabilir tüm [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) işlevlerinin tam olarak aynı şekilde davranması gerektiği anlamına gelir. Bu katıştırılmış nesnelerin "dış nesne" içindeki uygulamayı çağırması için bir geri işaretçi kullanılır (m_pParent). M_pParent işaretçisi CEditPrintObj Oluşturucusu sırasında başlatılır. Daha sonra CEditPrintObj:: CPrintObj::P rintObject ve CEditPrintObj:: CEditObj:: EditObject ' i de uygulamalısınız. Tek bir özellik eklemek için çok sayıda kod eklenmiştir — nesneyi düzenleme özelliği. Neyse ki, arabirimlerin yalnızca tek bir üye işlevi (gerçekleşse de) olması çok nadir bir durumdur ve bu durumda EditObject ve PrintObject genellikle tek bir arabirimde birleştirilir.

Bu, basit bir senaryo için çok fazla açıklama ve çok sayıda kod. MFC/OLE sınıfları daha basit bir alternatif sağlar. MFC Uygulama, Windows iletilerinin Ileti eşlemeleriyle Sarmalanma biçimine benzer bir teknik kullanır. Bu özellik, *arabirim haritaları* olarak adlandırılır ve sonraki bölümde açıklanmaktadır.

## <a name="mfc-interface-maps"></a>MFC Arabirim Eşlemeleri

MFC/OLE, kavram ve yürütme bölümünde MFC 'nin "Ileti eşlemeleri" ve "dağıtım haritaları" gibi "arabirim haritaları" uygulamasını içerir. MFC 'nin arabirim haritalarının temel özellikleri şunlardır:

- `CCmdTarget` Sınıfında yerleşik olarak bulunan [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)standart bir uygulamasıdır.

- Başvuru sayısının bakımı, [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) ve [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) tarafından değiştirildi

- Veri odaklı [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) uygulama

Ayrıca, arabirim haritaları aşağıdaki gelişmiş özellikleri destekler:

- Toplanabilir COM nesneleri oluşturma desteği

- Bir COM nesnesi uygulamasında toplama nesnelerini kullanma desteği

- Uygulama sabitlenebilir ve Genişletilebilir

Toplama hakkında daha fazla bilgi için [toplama](/windows/win32/com/aggregation) konusuna bakın.

MFC 'nin arabirim eşleme desteğiyle `CCmdTarget` sınıfında kök olarak yer verilir. `CCmdTarget`"*a*" başvuru sayısı ve [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) uygulamasıyla ilişkili tüm üye işlevleri ( `CCmdTarget`Örneğin, başvuru sayısı). OLE com destekleyen bir sınıf oluşturmak için, ' dan `CCmdTarget` bir sınıf türetirsiniz ve istenen arabirimleri uygulamak `CCmdTarget` için üye işlevlerinin yanı sıra çeşitli makroları kullanırsınız. MFC 'nin uygulama, yukarıdaki örnekte olduğu gibi her arabirim uygulamasını tanımlamak için iç içe geçmiş sınıfları kullanır. Bu, bir IUnknown standart uygulamasıyla ve yinelenen kodların bazılarını ortadan kaldıran birçok makro ile daha kolay hale getirilir.

## <a name="interface-map-basics"></a>Arabirim eşlemesi temelleri

### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>MFC 'nin arabirim eşlemelerini kullanarak bir sınıf uygulamak için

1. Doğrudan ya da dolaylı `CCmdTarget`olarak bir sınıf türet.

2. Türetilmiş sınıf tanımındaki işlevini kullanın. `DECLARE_INTERFACE_MAP`

3. Desteklemek istediğiniz her arabirim için, sınıf tanımında BEGIN_INTERFACE_PART ve END_INTERFACE_PART makrolarını kullanın.

4. Uygulama dosyasında, sınıfın arabirim haritasını tanımlamak için BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP makrolarını kullanın.

5. Desteklenen her IID için, BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP makroları arasındaki INTERFACE_PART makrosunu kullanarak bu IID 'yi sınıfınızın belirli bir "bölümüne" eşleyin.

6. Desteklenen arabirimleri temsil eden iç içe sınıfların her birini uygulayın.

7. Üst, `CCmdTarget`-türetilmiş nesnesine erişmek için METHOD_PROLOGUE makrosunu kullanın.

8. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) , `CCmdTarget` bu işlevlerin uygulanmasını temsil edebilir (`ExternalAddRef`, `ExternalRelease`ve `ExternalQueryInterface`).

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

Yukarıdaki bildirim, öğesinden `CCmdTarget`türetilmiş bir sınıf oluşturur. DECLARE_INTERFACE_MAP makrosu, çerçeveye bu sınıfın özel arabirim eşlemesine sahip olacağını söyler. Ayrıca, BEGIN_INTERFACE_PART ve END_INTERFACE_PART makroları iç içe geçmiş sınıfları tanımlar, bu durumda CEditObj ve CPrintObj adlarına sahiptir (X yalnızca, iç içe geçmiş sınıfları "C" ve arabirim sınıflarıyla başlayan genel sınıflardan ayırt etmek için kullanılır) "I" ile başlayın. Bu sınıfların iç içe geçmiş iki üyesi oluşturulur: sırasıyla m_CEditObj ve m_CPrintObj. Makrolar [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) işlevlerini otomatik olarak bildirir; Bu nedenle, yalnızca bu arabirime özgü işlevleri bildirirsiniz: EditObject ve PrintObject (OLE makrosu STDYÖNTEMI, **_stdcall** ve sanal anahtar sözcüklerin hedef platforma uygun şekilde sağlanması için kullanılır).

Bu sınıfa ait arabirim eşlemesini uygulamak için:

```cpp
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)
END_INTERFACE_MAP()
```

Bu, m_CPrintObj ve IID_IEditInterface ile IID_IPrintInterface IID 'yi sırasıyla m_CEditObj ile bağlar. `CCmdTarget` [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) ()`CCmdTarget::ExternalQueryInterface`uygulamasının uygulanması, m_CPrintObj ve m_CEditObj için işaretçi döndürmek üzere bu eşlemeyi kullanır. İçin `IID_IUnknown`bir giriş eklenmesi gerekli değildir; bu çerçeve, istendiğinde haritadaki ilk arabirimi (Bu örnekte m_CPrintObj `IID_IUnknown` ) kullanır.

BEGIN_INTERFACE_PART makrosu sizin için [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) işlevlerini otomatik olarak bildirse de onları uygulamanız gerekir:

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

Ayrıca Framework, dahili olarak ileti haritaları kullanır. Bu, belirli arabirimleri zaten destekleyen ve Framework tarafından sağlanan arabirimlere `COleServerDoc`değişiklik veya eklemeler sağlayan bir çerçeve sınıfından türetmeniz sağlar. Bu, Framework bir temel sınıftan arabirim haritasını devralmayı tam olarak desteklediği için yapabilirsiniz. Bunun nedeni, BEGIN_INTERFACE_MAP 'in ikinci parametre olarak temel sınıfın adı kadar sürme nedenidir.

> [!NOTE]
> MFC sürümünden söz konusu arabirimin gömülü özelleştirmesi devralınarak, MFC 'nin yerleşik uygulamalarının uygulamanın uygulama uygulamasının yerleşik uygulamalarını yeniden kullanmak mümkün değildir. Bu mümkün değildir çünkü içerilen `CCmdTarget`türetilmiş nesneye erişim elde etmek için METHOD_PROLOGUE makrosunun kullanımı, `CCmdTarget`türetilmiş nesnenin gömülü nesnesinin sabit bir *sapmasını* ifade etmez. Yani, örneğin, xadvisesink `COleClientItem::XAdviseSink` `COleClientItem` nesnenin en üstünden belirli bir uzaklığa bağlı olduğundan, MFC 'nin uygulamasındaki uygulamasından ekli bir xmyadvisesink türetilemez.

> [!NOTE]
> Ancak MFC 'nin varsayılan davranışını istediğiniz tüm işlevler için MFC uygulamasına temsilci atayabilirsiniz. Bu, `IOleInPlaceFrame` `COleFrameHook` sınıfındaki (XOleInPlaceFrame) MFC uygulamasında yapılır (birçok işlev için m_xOleInPlaceUIWindow 'e temsilciler). Bu tasarım, birçok arabirimi uygulayan nesnelerin çalışma zamanı boyutunu azaltmak için seçilmiştir; bir arka işaretçi gereksinimini ortadan kaldırır (örneğin, önceki bölümde m_pParent kullanıldığı gibi).

### <a name="aggregation-and-interface-maps"></a>Toplama ve arabirim haritaları

Tek başına COM nesnelerinin desteklenmesinin yanı sıra, MFC Ayrıca toplamayı da destekler. Toplama işlemi, burada tartışmak için çok karmaşık bir konudur; toplama hakkında daha fazla bilgi için [toplama](/windows/win32/com/aggregation) konusuna bakın. Bu notta, Framework ve arabirim eşlemlerinde yerleşik olarak bulunan toplama desteği açıklanır.

Toplamayı kullanmanın iki yolu vardır: (1) toplamayı destekleyen bir COM nesnesi kullanma ve (2) başka bir tarafından toplanabilecek bir nesne uygulama. Bu yetenekler "bir toplama nesnesi kullanma" ve "nesne toplanabilir hale getirme" olarak adlandırılabilir. MFC her ikisini de destekler.

### <a name="using-an-aggregate-object"></a>Toplama nesnesi kullanma

Bir toplama nesnesi kullanmak için, toplama yöntemini bir araya getirmek için bir yol olması gerekir. Diğer bir deyişle, toplama nesnesi, nesnenizin yerel bir parçası olsa da gibi davranmalıdır. Bu nedenle, iç içe yerleştirilmiş bir nesnenin bir IID ile eşlendiği INTERFACE_PART makrosunun yanı sıra MFC 'nin arabirim eşleme mekanizmasına nasıl bir araya yerleştiği, `CCmdTarget` türetilmiş sınıfınızın bir parçası olarak bir toplama nesnesi de bildirebilirsiniz. Bunu yapmak için, INTERFACE_AGGREGATE makrosu kullanılır. Bu, arabirim eşleme mekanizmasına tümleştirilecek bir üye değişkeni ( [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) veya türetilmiş bir sınıfa yönelik bir işaretçi olması gerekir) belirtmenize olanak tanır. Çağrıldığında işaretçi null `CCmdTarget::ExternalQueryInterface` değilse, işlem `IID` tarafından `IID` [](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) `CCmdTarget`desteklenenyerelöğeleriyoksa,çerçeveotomatikolaraktoplamanesnesininQueryInterfaceüyeişleviniçağırır.nesnenin kendisi.

#### <a name="to-use-the-interface_aggregate-macro"></a>INTERFACE_AGGREGATE makrosunu kullanmak için

1. Toplam nesnesine bir işaretçi içeren bir `IUnknown*`üye değişkeni (a) bildirin.

2. Ad ile üye değişkenine başvuran arabirim haritanızda bir INTERFACE_AGGREGATE makrosu ekleyin.

3. Bir noktada (genellikle sırasında `CCmdTarget::OnCreateAggregates`), üye değişkenini null dışında bir şeye başlatın.

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

M_lpAggrInner değişkeni oluşturucuda NULL olarak başlatılır. Çerçeve, varsayılan [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))UYGULAMASıNDA bir null üye değişkenini yoksayar. `OnCreateAggregates`Aslında toplama nesnelerinizi oluşturmak için iyi bir yerdir. Nesneyi MFC uygulamasının `COleObjectFactory`dışında oluşturuyorsanız, bunu açıkça çağırmanız gerekir. ' De toplama oluşturma nedeni ve `CCmdTarget::OnCreateAggregates` ' nin `CCmdTarget::GetControllingUnknown` kullanımı, toplanılan nesneleri oluştururken görünür hale gelir.

Bu teknik, nesnenizin toplama nesnesinin desteklediği tüm arabirimlerin yanı sıra kendi yerel arabirimlerini sağlayacaktır. Yalnızca toplamanın desteklediği arabirimlerin bir alt kümesini isterseniz, geçersiz kılabilirsiniz `CCmdTarget::GetInterfaceHook`. Bu, [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))'e benzer bir çok düşük düzey hookability sağlar. Genellikle, toplamanın desteklediği tüm arabirimlerin olmasını istersiniz.

### <a name="making-an-object-implementation-aggregatable"></a>Bir nesne uygulamasını toplanabilir hale getirme

Bir nesnenin toplanabilir olması için [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) uygulamasının bir "denetleme bilinmiyor" ile temsilci seçme gerekir. Diğer bir deyişle, nesnenin bir parçası olması için [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) 'i aynı zamanda [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)'ten türeten farklı bir nesneye vermelidir. Bu "denetimi bilinmiyor", oluşturulduğunda nesnesine sağlanır, diğer bir deyişle, uygulamasının uygulamasına `COleObjectFactory`sağlanır. Bunu uygulamak, az miktarda yük taşır ve bazı durumlarda istenen değildir, bu nedenle MFC bunu isteğe bağlı hale getirir. Bir nesnenin toplanabilir olmasını sağlamak için nesnenin yapıcısını çağırın `CCmdTarget::EnableAggregation` .

Nesne ayrıca toplamalar kullanıyorsa, doğru "denetimi bilinmiyor" öğesini de toplam nesnelere iletdiğinizden emin olmanız gerekir. Toplama oluşturulduğunda genellikle bu [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) işaretçisi nesnesine geçirilir. Örneğin, pUnkOuter parametresi ile `CoCreateInstance`oluşturulan nesneler için "bilinmeyen denetim" dir. Doğru "Denetim bilinmiyor" işaretçisi çağırarak `CCmdTarget::GetControllingUnknown`elde edilebilir. Ancak, bu işlevden döndürülen değer, Oluşturucu sırasında geçerli değildir. Bu nedenle, toplamanızı yalnızca bir geçersiz kılmada `CCmdTarget::OnCreateAggregates`oluşturmanız önerilir, burada dönüş `GetControllingUnknown` değeri uygulamadan oluşturulmuş `COleObjectFactory` olsa bile güvenilir.

Ayrıca, yapay başvuru sayılarını eklerken veya serbest bırakırken nesnenin doğru başvuru sayısını işlemesinin önemli olması da önemlidir. Bunun durumu olduğundan emin olmak `ExternalAddRef` için, `InternalRelease` ve `ExternalRelease` `InternalAddRef`yerine her zaman çağırın. Toplamayı destekleyen bir sınıf üzerinde `InternalRelease` veya `InternalAddRef` çağırmak nadir olarak belirlenir.

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

Bu makroyu, bir arabirim eşlemesine sahip `CCmdTarget` olan sınıfından türetilmiş herhangi bir sınıfta kullanın. DECLARE_MESSAGE_MAP ile aynı şekilde kullanılır. Bu makro çağrısı, genellikle bir üst bilgide (. H) dosyası. DECLARE_INTERFACE_MAP içeren bir sınıf, uygulama dosyasında arabirim eşlemesini tanımlamalıdır (. CPP) BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP makroları.

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

Sınıfınızın uygulayabileceği her arabirim için bir BEGIN_INTERFACE_PART ve END_INTERFACE_PART çiftinin olması gerekir. Bu makrolar, tanımladığınız OLE arabiriminden ve bu sınıfın gömülü üye değişkenine türetilmiş bir yerel sınıf tanımlar. [AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref), [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release)ve [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) üyeleri otomatik olarak bildirilmiştir. Uygulanan arabirimin parçası olan diğer üye işlevleri için bildirimleri dahil etmeniz gerekir (Bu bildirimler BEGIN_INTERFACE_PART ve END_INTERFACE_PART makroları arasına yerleştirilir).

*İface* bağımsız değişkeni `IAdviseSink`, veya `IPersistStorage` (veya kendi özel arabiriminiz) gibi uygulamak istediğiniz OLE arabirimidir.

*LocalClass* bağımsız değişkeni, tanımlanacaktır yerel sınıfın adıdır. Ada bir ' X ' otomatik olarak eklenecek. Bu adlandırma kuralı, aynı ada sahip genel sınıflarla çakışmaları önlemek için kullanılır. Ayrıca, gömülü üyenin adı, *localClass* adı ile aynı, yani ' ı ' tarafından önek olarak 'm _X ' öğesine eklenir.

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
> _ İle `STDMETHOD`başlayan satırlar aslında OLE2 öğesinden kopyalanır. H ve biraz daha değiştirildi. OLE2 adresinden kopyalanıyor. H, çözülmesi zor olan hataları azaltabilir.

### <a name="begin_interface_map-and-end_interface_map--macro-descriptions"></a>BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP — makro açıklamaları

```cpp
BEGIN_INTERFACE_MAP(theClass, baseClass)
END_INTERFACE_MAP
```

#### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Arabirim eşlemesinin tanımlanması gereken sınıf

*baseClass*<br/>
Sınıfı 'ın türetildiği sınıf.

#### <a name="remarks"></a>Açıklamalar

BEGIN_INTERFACE_MAP ve END_INTERFACE_MAP makroları, arabirim eşlemesini gerçekten tanımlamak için uygulama dosyasında kullanılır. Uygulanan her arabirim için bir veya daha fazla INTERFACE_PART makro çağırmaları vardır. Sınıfın kullandığı her bir toplama için bir INTERFACE_AGGREGATE makro çağrısı vardır.

### <a name="interface_part--macro-description"></a>INTERFACE_PART — makro açıklaması

```cpp
INTERFACE_PART(theClass, iid, localClass)
```

#### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Arabirim eşlemesini içeren sınıfın adı.

*'si*<br/>
`IID` Katıştırılmış sınıfa eşlenecek.

*localClass*<br/>
Yerel sınıfın adı (' X ' daha az).

#### <a name="remarks"></a>Açıklamalar

Bu makro, nesnenizin destekleyeceği her arabirim için BEGIN_INTERFACE_MAP makrosu ve END_INTERFACE_MAP makrosu arasında kullanılır. Bir IID 'yi, sınıfsınıfı ve *localClass*tarafından belirtilen sınıfın bir üyesine eşlemenizi sağlar. 'M _X ', *localClass* 'a otomatik olarak eklenecektir. Birden fazla `IID` üyenin tek bir üyeyle ilişkili olabileceğini unutmayın. Yalnızca bir "en çok türetilmiş" arabirimi uyguladığınızda ve tüm ara arabirimleri sağlamak istediğinizde bu çok yararlı olur. Bu `IOleInPlaceFrameWindow` arabirimin iyi bir örneğidir. Hiyerarşisi şuna benzer:

```Hierarchy
IUnknown
    IOleWindow
        IOleUIWindow
            IOleInPlaceFrameWindow
```

Bir nesne uygularsa `IOleInPlaceFrameWindow`, "en türetilmiş `QueryInterface` " arabiriminin `IOleInPlaceFrameWindow` yanı sıra, bir `IOleUIWindow`istemci `IOleWindow`şu arabirimlerin herhangi birinde olabilir:, veya [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)(aslında sizin uyguladıysanız). Bunu işlemek için birden fazla INTERFACE_PART makrosunu kullanarak her bir temel arabirimi `IOleInPlaceFrameWindow` arabirime eşleyin:

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

Bu makro, çerçeveye sınıfın bir toplama nesnesi kullandığını bildirmek için kullanılır. BEGIN_INTERFACE_PART ve END_INTERFACE_PART makroları arasında görünmesi gerekir. Toplama nesnesi, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)öğesinden türetilen ayrı bir nesnedir. Bir toplama ve INTERFACE_AGGREGATE makrosunu kullanarak, toplamanın desteklediği tüm arabirimlerin nesne tarafından doğrudan desteklendiğinden görünmesini sağlayabilirsiniz. IBU bağımsız değişken, yalnızca [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 'dan türetilmiş (doğrudan veya dolaylı olarak) sınıfınızın üye değişkeninin adıdır. Tüm INTERFACE_AGGREGATE makroları, bir arabirim eşlemesine yerleştirildiğinde INTERFACE_PART makrolarını izlemelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
