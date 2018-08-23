---
title: 'TN038: MFC-OLE IUnknown uygulaması | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acf33139250e6876dde6d86f7e8ed144dbe23180
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42465836"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038: MFC/OLE IUnknown Uygulaması

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

OLE 2 öğesinin temelinde "OLE bileşik nesne modeli" veya COM vardır. COM bir standardı tanımlar için nasıl birlikte çalışan nesnelerin birbirleriyle iletişim. Bu, bir "nesne", bir nesne üzerinde yöntemleri nasıl gönderilir dahil olmak üzere nasıl göründüğünü ayrıntılarını içerir. COM, ayrıca, tüm COM uyumlu sınıflar türetilmiş bir temel sınıf tanımlar. Bu temel sınıf [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Ancak [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) arabiriminin C++ sınıfı olarak adlandırılır, COM, herhangi bir dile özgü değildir — C, PASCAL veya COM nesnesinin ikili düzenini destekleyen başka bir dilde uygulanabilir.

OLE öğesinden türetilmiş tüm sınıflara başvurur [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) "arabirimler" olarak Bu önemli bir ayrımdır bir "arabirim" olduğu gibi [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ile hiçbir uygulama taşımadığından. Yalnızca nesnelerin iletişim, bu uygulamaları neler özellikleri değil protokol da tanımlar. Bu maksimum esnekliğe olanak sisteminin şüphelenilebilir. MFC/C++ programları için varsayılan davranışı uygulayan MFC görevidir işidir.

MFC'nin uygulanmasını anlamak için [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) önce arabirimin ne olduğunu anlamanız gerekir. Basitleştirilmiş bir sürümünü [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) aşağıda tanımlanmıştır:

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
> Gibi belirli gerekli çağrı kuralı ayrıntıları `__stdcall` Bu resimde solda gösterilmiştir.

[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317) üye işlevleri nesnenin bellek yönetimini denetler. COM, nesneleri izlemek için başvuru sayım düzenini kullanır. Nesne hiçbir zaman başvurulan C++ içinde olduğu gibi doğrudan. Bunun yerine, COM nesneleri her zaman bir işaretçi ile başvurulur. Sahibi bittiğinde nesneyi serbest bırakmak onun, nesne kullanarak [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317) üyesi (için geleneksel bir C++ nesnesinde olduğu gibi işleç silmenin kullanılması yerine) çağrılır. Başvuru sayım mekanizması yönetilmesi için tek bir nesneye birden çok başvuru için sağlar. Uygulanışı [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317) nesnede başvuru sayısını tutar — nesne, başvuru sayısı sıfır oluncaya kadar silinmez.

[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317) uygulama açısından oldukça basittir. Basit bir uygulama şu şekildedir:

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

[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) üye işlevi biraz daha ilginçtir. Yalnızca üye işlevleri olan bir nesneye çok ilginç değil [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317) — fazla daha fazla bir şeyler yapmasını söylemek de iyi [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) sağlar. Burada [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) yararlıdır. Farklı bir "arabirim" aynı nesne üzerinde almanızı sağlar. Bu arabirimler genellikle türetilmiştir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ve yeni üye işlevleri ekleyerek ek işlevler ekleyin. COM arabirimleri arabirimde bildirilen üye değişkenlerine hiçbir zaman sahiptir ve tüm üye işlevleri saf sanal olarak bildirilir. Örneğin,

```cpp
class IPrintInterface : public IUnknown
{
public:
    virtual void PrintObject() = 0;
};
```

Yalnızca varsa bir Iprintınterface edinmek için bir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), çağrı [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) kullanarak `IID` , `IPrintInterface`. Bir `IID` arabirimi benzersiz olarak tanımlayan 128-bit sayıdır. Var olan bir `IID` siz veya OLE'nin tanımladığı her arabirim için. Varsa *pUnk* işaretçisidir bir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) nesnesi, kodu bir ondan ıprintınterface olabilir:

```cpp
IPrintInterface* pPrint = NULL;
if (pUnk->QueryInterface(IID_IPrintInterface, (void**)&pPrint) == NOERROR)
{
    pPrint->PrintObject();
    pPrint->Release();
    // release pointer obtained via QueryInterface
}
```

Bu oldukça kolay görünüyor, ancak nasıl uygulardınız hem Iprintınterface destekleyen bir nesneyi ve [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) arabirimi Iprintınterface doğrudan'dan türetilmiş olduğundan bu durumda basittir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) — ıprintınterface uygulamasıyla [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) otomatik olarak desteklenir. Örneğin:

```cpp
class CPrintObj : public CPrintInterface
{
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);
    virtual ULONG AddRef();
    virtual ULONG Release();
    virtual void PrintObject();
};
```

Uygulamaları [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317) tam olarak aynı uygulananlarla yukarıdaki olması. `CPrintObj::QueryInterface` şunun gibi görünür:

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

Arabirim tanımlayıcısı (IID) tanımlıysa, gördüğünüz gibi bir işaretçi nesnenize döner; Aksi takdirde hata oluşur. Ayrıca başarılı bir [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) sonuçları örtülü bir [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379). Kuşkusuz, CEditObj::Print uygulamak de gerekir. Iprintınterface doğrudan türetildiği basit olan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) arabirimi. İki farklı arayüzü desteklemek isterseniz, ancak her ikisini de türetilmiş [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), aşağıdakileri dikkate alın:

```cpp
class IEditInterface : public IUnkown
{
public:
    virtual void EditObject() = 0;
};
```

Birkaç Ieditınterface hem de C++ birden çok devralma ıprintınterface öğelerini destekleyen bir sınıf uygulamak için farklı yol olmasına rağmen bu Not Bu işlevselliği uygulamak için iç içe geçmiş sınıflar kullanımını odaklanacaktır.

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

Tüm uygulama aşağıda yer almaktadır:

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

Çoğu fark [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) uygulama CEditPrintObj sınıfı içine yerleştirilen CEditPrintObj::CEditObj ve CEditPrintObj::CPrintObj kodunu çoğaltmak yerine. Bu kod miktarını azaltır ve hataları önler. Burada temel nokta IUnknown arabirimden, çağrı mümkün olmasıdır [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) arabirimi almak için nesnenin destekleyebildiği ve o arabirimlerin her birinden yapmak mümkündür. Bunun anlamı tüm [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) her arabiriminden işlevleri tamamen aynı şekilde davranması gerekir. Sırayla bu katıştırılmış nesnelerin "dış nesne" içinde uygulamayı çağırması bir arka işaretçi kullanılır (m_pParent) ' dir. M_pParent işaretçisi CEditPrintObj Oluşturucusu sırasında başlatılır. Sonra ceditprintobj::cprintobj:: PrintObject ve CEditPrintObj::CEditObj::EditObject de uygulayabilir. Bir özellik eklemek için tam anlamıyla bir bit kod eklendi — nesneyi düzenleme yeteneği. Neyse ki, (böyle bir durum olsa da) yalnızca tek bir üye işlevi olan arabirimler için bu oldukça seyrek olur ve bu durumda, EditObject ve PrintObject genellikle tek bir arabirim olarak birleştirilir.

Oldukça fazla açıklama ve kod basit bir senaryo için çok fazla olmasıdır. MFC/OLE sınıfları daha basit bir alternatif sağlar. MFC uygulaması, ileti eşlemeleri ile benzer şekilde Windows iletileri sarmalanmış bir teknik kullanır. Bu adlandırılmaktadır *arabirim eşlemeleri* ve sonraki bölümde ele alınmıştır.

## <a name="mfc-interface-maps"></a>MFC arabirim eşlemeleri

MFC/OLE, kavram ve yürütmede MFC'nin "İleti eşlemeleri" ve "Gönderme eşlemeleri" benzer "arabirimi haritaları" uygulaması içerir. MFC'nin arabirim eşlemeleri'nin temel özellikleri aşağıda verilmiştir:

- Öğesinin standart uygulaması [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), yerleşik `CCmdTarget` sınıfı.

- Tarafından değiştirilen başvuru sayısı Bakımı [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317)

- Veri odaklı uygulaması [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)

Ayrıca, arabirim eşlemeleri aşağıdaki gelişmiş özellikleri destekler:

- Bir araya toplanabilir COM nesneleri oluşturma desteği

- Bir COM nesnesinin uygulamasında toplama nesnelerini kullanma desteği

- Uygulama sabitlenebilir ve Genişletilebilir özelliktedir

Toplama hakkında daha fazla bilgi için bkz. [toplama](/windows/desktop/com/aggregation) konu.

MFC'nin arabirimi eşleme desteğinin kökü `CCmdTarget` sınıfı. `CCmdTarget` "*sahip bir*" başvuru sayısı yanı sıra tüm üye işlevleri ilişkili [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) uygulama (bulunduğu örneğin başvuru sayısı `CCmdTarget`). OLE COM'u destekleyen bir sınıf oluşturmak için öğesinden bir sınıf türetin `CCmdTarget` ve çeşitli makroları üye işlevlerini `CCmdTarget` ve istenen arabirimleri gerçekleştirmek için. MFC'nin uygulaması, yukarıdaki örnek gibi her arabirim uygulamasını tanımlamak için iç içe geçmiş sınıflar kullanır. IUnknown yanı sıra bazı yinelenen kodları ortadan makroları bir dizi standart uygulaması ile daha kolay yapılır.

## <a name="interface-map-basics"></a>Arabirim eşlemesi temelleri

### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>MFC'nin arabirimi kullanarak bir sınıf uygulamak için eşler.

1. Doğrudan veya dolaylı olarak bir öğesinden bir sınıf türetin `CCmdTarget`.

2. Kullanım `DECLARE_INTERFACE_MAP` türetilmiş sınıf tanımında işlevi.

3. Desteklemek istediğiniz her arayüz için sınıf tanımında begın_ınterface_part ve end_ınterface_part makroları kullanın.

4. Uygulama dosyasında begın_ınterface_map ve end_ınterface_map makrolarını sınıfın arabirim haritasını tanımlamak için kullanın.

5. Interface_part makrosu o IID'yi sınıfınızın "bölümüne" belirli eşlemek için begın_ınterface_map ve end_ınterface_map makroları arasında desteklenen her IID için kullanın.

6. Desteklediğiniz arabirimleri temsil eden iç içe geçmiş sınıfların her birini uygulayın.

7. METHOD_PROLOGUE makrosu üst üzere `CCmdTarget`-türetilmiş bir nesneye.

8. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) temsilci seçmek için kullanabileceği `CCmdTarget` uygulama bu işlevlerin (`ExternalAddRef`, `ExternalRelease`, ve `ExternalQueryInterface`).

Yukarıdaki CPrintEditObj örneği şu şekilde uygulanabilir:

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

Yukarıdaki bildirim, türetilen bir sınıf oluşturur `CCmdTarget`. Declare_ınterface_map makrosu framework, bu sınıfın özel arabirim eşlemesine sahip olacağını belirtir. Ayrıca, begın_ınterface_part ve end_ınterface_part makroları iç içe geçmiş sınıflar, bu durumda CEditObj ve CPrintObj (X yalnızca yuvalı sınıfları "C" ve arabirimi ile hangi başlangıç hangi sınıfların global sınıflardan ayırt etmek için kullanılan adlarla tanımlayın "I" ile başlayan). Bu sınıfların iki iç içe üyesi oluşturuldu: sırasıyla m_CEditObj ve m_CPrintObj, sırasıyla. Makroları otomatik olarak bildirin [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) çalışır; bu nedenle, yalnızca işlevler bu arabirime özgü bildirmek: EditObject ve PrintObject (OLE makrosu STDMETHOD kullanılan böylece **_stdcall** ve sanal anahtar sözcüklerinin hedef platform için uygun şekilde).

Bu sınıfa ilişkin arabirim eşlemesini uygulamak için:

```cpp
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)
END_INTERFACE_MAP()
```

Bu sırasıyla ııd_ıprintınterface IID'yi m_CPrintObj ile ııd_ıeditınterface'ı da m_CEditObj ile bağlar. `CCmdTarget` Uygulaması [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) (`CCmdTarget::ExternalQueryInterface`) m_CPrintObj ve m_CEditObj istendiğinde işaretçilerini döndürmek için bu eşlemesini kullanır. İçin bir girdi eklenmesi gerekli değildir `IID_IUnknown`; çerçevesi (Bu durumda, m_CPrintObj) haritadaki ilk arabirimi zaman kullanacağı `IID_IUnknown` istenir.

Begın_ınterface_part makrosu otomatik olarak bildirilmiş olsa bile [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317) ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) işlevlerini sizin, hala bunları uygulamanız gerekir:

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

Ceditprintobj::cprintobj uygulaması, olacaktır CEditPrintObj::CEditObj için yukarıdaki tanımlarla benzer. Bu işlevleri otomatik olarak oluşturmak için kullanılabilecek bir makro (ancak daha önce MFC/OLE geliştirmesinde bu oluşturulabilmesine rağmen), bir makro birden fazla kod satırı oluşturduğunda kesme noktalarını ayarlamak zordur. Bu nedenle, bu kod el ile genişletilir.

İleti eşlemelerinin framework uygulamasını kullanarak yapmanız gerekli olmayan etmenizi vardır:

- QueryInterface Uygula

- AddRef ve Release uygulayın

- Arabirimlerinizin ikisinde bu yerleşik yöntemlerden birini bildirin

Ayrıca, framework dahili ileti eşlemelerini kullanır. Bu sayede bir framework sınıfından, örneğin türetmek `COleServerDoc`, zaten belirli arabirimleri destekleyen ve değişiklik veya eklemeleri için framework tarafından sağlanan arabirimleri sağlar. Arabirim eşlemesine bir temel sınıftan devralmayı tam olarak framework desteklediği için bunu yapabilirsiniz. Neden begın_ınterface_map temel sınıfın adını, ikinci parametre olarak alır. neden olmasıdır.

> [!NOTE]
> Genellikle yalnızca MFC sürümü bu arabirimin katıştırılmış uzmanlığı devralarak MFC'nin yerleşik uygulamalarının OLE arabirimleri uygulamasını yeniden kullanmak mümkün değildir. Bu mümkün değildir çünkü içeren erişimi elde etmek METHOD_PROLOGUE makrosu kullanımını `CCmdTarget`-türetilmiş nesneden gelir bir *sabit uzaklığı* katıştırılmış nesne, `CCmdTarget`-türetilmiş bir nesneye. Bu, örneğin, MFC'nin gelen katıştırılmış bir XMyAdviseSink türeyemez anlamına gelir `COleClientItem::XAdviseSink`, çünkü XAdviseSink üstünden belirli bir uzaklıkta dayanır `COleClientItem` nesne.

> [!NOTE]
> Ancak, tüm işlevleri MFC'nin varsayılan davranışı olmasını istediğiniz MFC uygulamasını temsilci olabilir. Bu öğesinin MFC uygulamasında yapılır `IOleInPlaceFrame` (Xoleınplaceframe) içinde `COleFrameHook` sınıfı (Bu temsilcilerin m_xOleInPlaceUIWindow çok işlev için). Bu tasarım, pek çok arabirimi uygulayan nesnelerin çalışma zamanı boyutunu küçültmek için seçilmiştir; (önceki bölümde şekilde m_pParent kullanılan gibi) geri işaretçisi gereksinimini ortadan kaldırır.

### <a name="aggregation-and-interface-maps"></a>Toplama ve arabirim eşlemeleri

Tek başına COM nesnelerini desteklemenin yanı sıra, MFC toplamayı da destekler. Toplama, başlı başına burada tartışmak için çok karmaşık bir konudur; başvurmak [toplama](/windows/desktop/com/aggregation) toplama hakkında daha fazla bilgi için konu. Bu not yalnızca çerçeve ve arabirim eşlemelerinde yerleşik olan toplama için desteği açıklanmaktadır.

Toplamanın iki yolu vardır: (1) toplamayı destekleyen COM nesnesi kullanma ve (2) başkası tarafından toplanabilir nesneyi uygulama. Bu özellikler için "Toplam nesnesi kullanma" ve "bir nesnenin toplanabilir yapma" olarak adlandırılır. MFC her ikisini de destekler.

### <a name="using-an-aggregate-object"></a>Toplam nesnesi kullanma

Bazı yollar toplam içine QueryInterface mekanizmasına bağlanacak bir toplam değer nesnesi kullanmak için. Diğer bir deyişle, nesnenizin yerel bir parçası olsa olarak toplam nesnenin davranmalıdırlar. Nasıl MFC'nin arabirim eşleme mekanizmasının ınterface_part makrosu yanı sıra halinde bu KRAVAT mu yuvalı nesnenin IID'ye eşlendiği yerlerde de bildirebilirsiniz bir toplama nesnesi bir parçası olarak, `CCmdTarget` türetilmiş sınıf. Bunu yapmak için ınterface_aggregate makrosunu kullanılır. Bu, bir üye değişkeni belirtmenize olanak sağlar (bir işaretçi olmalıdır bir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) sınıfa veya türetilmiş), arabirim eşleme mekanizmasına tümleştirilecek olduğu. İşaretçi olduğunda NULL değilse `CCmdTarget::ExternalQueryInterface` olan çağrılır, çerçeve otomatik olarak toplam nesnenin çağıracak [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) üye işlevini, `IID` istenen biri yerel değil `IID`s tarafından desteklenen `CCmdTarget` nesnenin kendisi.

#### <a name="to-use-the-interfaceaggregate-macro"></a>Interface_aggregate makrosunu kullanmak için

1. Üye değişkeni bildirme (bir `IUnknown*`) toplama nesnesine bir işaretçi içerir.

2. Interface_aggregate makrosunu üye değişkenine adıyla başvuran arabirim eşlemenize ekleyin.

3. Belirli bir noktada (genellikle sırasında `CCmdTarget::OnCreateAggregates`), üye değişkeninin NULL dışında bir şey.

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

M_lpaggrınner değişkeni oluşturucuda null ile başlatılır. Framework varsayılan uygulamasında bir NULL üye değişkenini yoksayar [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). `OnCreateAggregates` Aslında, toplam değer nesneleri oluşturmak için uygun bir yerdir. Nesne MFC uygulaması dışında oluşturuyorsanız bunu açıkça çağırmanız gerekecektir `COleObjectFactory`. İçinde toplamlar oluşturma nedeni `CCmdTarget::OnCreateAggregates` kullanımını yanı sıra `CCmdTarget::GetControllingUnknown` toplanabilir nesneler oluşturma işlemi tartışılırken anlaşılacaktır.

Bu teknik nesnenizin toplam nesnenin kendi yerel arabirimleri ile birlikte desteklediği arabirimlerin tümünü sunar. Yalnızca bir alt toplamanın desteklediği arabirimlerin istiyorsanız, geçersiz kılabilirsiniz `CCmdTarget::GetInterfaceHook`. Çok düşük düzeyli hookability, benzer şekilde bu sayede [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). Genellikle toplam destekleyen tüm arabirimleri istersiniz.

### <a name="making-an-object-implementation-aggregatable"></a>Bir nesne uygulamasını toplanabilir yapma

Toplanabilir olması bir nesne uygulanması için [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) bir "denetleyen bilinmeyendir için." temsilci gerekir Diğer bir deyişle, bu nesnenin bir parçası olarak temsilci gerekir [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) farklı bir nesneye de türetilmiş [ IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Bu "kontrol eden bilinmeyen" oluşturulduğunda, nesnenin başka bir deyişle, bu öğesinin uygulanmasına sağlanır sağlanır `COleObjectFactory`. Bu uygulama az miktarda bir ek yük getirir ve MFC bunu isteğe bağlı hale getirir bu nedenle bazı durumlarda istenmez, değil. Bir nesnenin toplanabilir olması etkinleştirmek için çağrı `CCmdTarget::EnableAggregation` nesnenin oluşturucusundan.

Nesne de toplamları kullanıyorsa de doğru aktardığınızdan emin olmalısınız "denetleyen bilinmeyendir" öğesini toplam nesnelere. Genellikle bu [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) işaretçisi toplama oluşturulduğunda nesneye geçirilir. Örneğin pUnkOuter parametresi "denetleyen bilinmeyendir" ile oluşturulan nesneler için olan `CoCreateInstance`. Doğru "kontrol eden bilinmeyen" işaretçisi çağrılarak alınabilir `CCmdTarget::GetControllingUnknown`. O işlevden döndürülen değer ancak Oluşturucu sırasında geçerli değil. Bu nedenle toplamalarınızı yalnızca geçersiz kılma oluşturmanız önerilir `CCmdTarget::OnCreateAggregates`, dönüş değeri burada `GetControllingUnknown` oluşturulan bile güvenilirdir `COleObjectFactory` uygulaması.

Nesnenin doğru başvuru sayısı eklerken veya yapay başvuru sayısı düzenlemesi de önemlidir. Bunun olmasını sağlamak için her zaman çağrı `ExternalAddRef` ve `ExternalRelease` yerine `InternalRelease` ve `InternalAddRef`. Nadiren `InternalRelease` veya `InternalAddRef` toplamayı destekleyen bir sınıf.

## <a name="reference-material"></a>Başvuru malzemesi

OLE, kendi arabirimlerinizi belirlemek veya OLE arabirimlerinin framework uygulamalarını geçersiz kılmak gibi gelişmiş kullanımı temel arabirim eşleme mekanizmasının kullanımını gerektirir.

Bu bölümde, her makro ve bu Gelişmiş özellikleri uygulamak için kullanılan API'leri ele alınmaktadır.

### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget::EnableAggregation — İşlev açıklaması

```cpp
void EnableAggregation();
```

#### <a name="remarks"></a>Açıklamalar

Bu türün nesneleri için OLE toplama desteklemek isterseniz türetilen sınıfın oluşturucusunda bu işlevi çağırın. Bu, toplanabilir nesneler için gerekli olan özel bir IUnknown uygulaması hazırlar.

### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget::externalqueryınterface — İşlev açıklaması

```cpp
DWORD ExternalQueryInterface(
    const void FAR* lpIID,
    LPVOIDFAR* ppvObj
);
```

#### <a name="parameters"></a>Parametreler

*lpIID*  
(Queryınterface'in ilk bağımsız değişken) IID öğesine Uzak İşaretçi

*ppvObj*  
Bir IUnknown * işaretçi (Queryınterface'in ikinci bağımsız değişkeni)

#### <a name="remarks"></a>Açıklamalar

Bu işlev her arabirim için IUnknown uygulamanızda, kendi sınıfınızı çağırın. uygular. Bu işlev, nesnenizin arabirimi haritasına dayalı QueryInterface standart veri odaklı uygulamasını sağlar. HRESULT dönüş değerini'değerine dönüştürme gereklidir. Nesne toplanırsa, bu işlev yerel arabirim eşlemesini değiştirmek yerine "IUnknown denetimi" çağıracaktır.

### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget::ExternalAddRef — İşlev açıklaması

```cpp
DWORD ExternalAddRef();
```

#### <a name="remarks"></a>Açıklamalar

Bu işlev her arabirim için IUnknown::AddRef uygulamanızda, kendi sınıfınızı çağırın. uygular. Yeni başvuru sayısını CCmdTarget nesnenin dönüş değeridir. Nesne toplanırsa, bu işlev yerel başvuru sayısını değiştirmek yerine "IUnknown denetimi" çağıracaktır.

### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget::ExternalRelease — İşlev açıklaması

```cpp
DWORD ExternalRelease();
```

#### <a name="remarks"></a>Açıklamalar

Bu işlev her arabirim için IUnknown::Release uygulamanızda, kendi sınıfınızı çağırın. uygular. Dönüş değeri yeni nesneye başvuru sayısını gösterir. Nesne toplanırsa, bu işlev yerel başvuru sayısını değiştirmek yerine "IUnknown denetimi" çağıracaktır.

### <a name="declareinterfacemap--macro-description"></a>Declare_ınterface_map — Makro tanımı

```cpp
DECLARE_INTERFACE_MAP
```

#### <a name="remarks"></a>Açıklamalar

Öğesinden türetilen sınıfta Bu makroyu kullanın `CCmdTarget` arabirim eşlemesine sahip olur. Çok DECLARE_MESSAGE_MAP aynı şekilde kullanılır. Bu makro çağırma sınıf tanımına, genellikle bir üst bilgisindeki yerleştirilmelidir (. H) dosyası. Declare_ınterface_map sahip sınıf uygulama dosyasında arabirim haritasını tanımlamak gerekir (. CPP) begın_ınterface_map ve end_ınterface_map makroları ile.

### <a name="begininterfacepart-and-endinterfacepart--macro-descriptions"></a>Begın_ınterface_part ve end_ınterface_part — makro

```cpp
BEGIN_INTERFACE_PART(localClass, iface);
END_INTERFACE_PART(localClass)
```

#### <a name="parameters"></a>Parametreler

*localClass*  
Arabirimini uygulayan sınıfın adı

*iface*  
Bu sınıfın uyguladığı arabirimin adı

#### <a name="remarks"></a>Açıklamalar

Sınıfınızın uygulayacağı her arayüz için bir begın_ınterface_part ve end_ınterface_part çift olması gerekir. Bu makrolar yanı sıra söz konusu sınıfın bir katıştırılmış bir üye değişkenini tanımladığınız OLE arabiriminden türetilen yerel bir sınıfı tanımlar. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) üyeleri otomatik olarak bildirilir. Uygulanan arabiriminin bir parçası olan diğer üye işlevler için bildirimler eklemeniz gerekir (Bu bildirimler begın_ınterface_part ve end_ınterface_part makroları arasında yer alır).

*İface* bağımsız değişken olduğu gibi uygulamak istediğiniz OLE arabirimidir `IAdviseSink`, veya `IPersistStorage` (veya kendi özel arabiriminiz).

*LocalClass* bağımsız değişkeni tanımlanacak yerel sınıfın adıdır. Bir'X ' adına otomatik olarak eklenir. Bu adlandırma kuralı, aynı ada sahip genel sınıflarla çakışmaları önlemek için kullanılır. Ayrıca katıştırılmış üyenin adını, aynı *localClass* 'm_x' öneki almasının dışında adlandırın.

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

Iadvisesink'ten türetilmiş XMyAdviseSink adlı bir yerel sınıf ve içinde bildirildiği bir sınıfın üyesi m_xMyAdviseSink.Note adlı:

> [!NOTE]
> İle başlayan satırlar `STDMETHOD`_ i OLE2'ye temelde kopyalanır. H ve biraz değiştirilmiş. OLE2 kopyalayarak. H çözülmesi zor hataları azaltabilir.

### <a name="begininterfacemap-and-endinterfacemap--macro-descriptions"></a>Begın_ınterface_map ve end_ınterface_map — makro

```cpp
BEGIN_INTERFACE_MAP(theClass, baseClass)
END_INTERFACE_MAP
```

#### <a name="parameters"></a>Parametreler

*Sınıfın*  
Arabirim eşlemesi tanımlanmış olduğu sınıfı

*baseClass*  
Sınıf *sınıfın* türetir.

#### <a name="remarks"></a>Açıklamalar

Begın_ınterface_map ve end_ınterface_map makroları, aslında arabirim haritasını tanımlamak için uygulama dosyasında kullanılır. Uygulanan her arabirim için bir veya daha fazla ınterface_part makrosu çağrılarını yoktur. Sınıfın kullandığı her toplama için bir ınterface_aggregate makro çağrısı vardır.

### <a name="interfacepart--macro-description"></a>Interface_part — Makro tanımı

```cpp
INTERFACE_PART(theClass, iid, localClass)
```

#### <a name="parameters"></a>Parametreler

*Sınıfın*  
Arabirim eşlemesini içeren sınıfın adı.

*IID*  
`IID` Katıştırılmış sınıfla eşleştirilecek olmasıdır.

*localClass*  
(' X') daha az yerel sınıfın adı.

#### <a name="remarks"></a>Açıklamalar

Bu makro, nesnenizin destekleyeceği her arabirim için makro begın_ınterface_map ve end_ınterface_map makrosu arasında kullanılır. Tarafından belirtilen bir sınıf üyesi için bir IID eşlemenizi sağlar *sınıfın* ve *localClass*. 'm_x' eklenecek *localClass* otomatik olarak. Birden fazla Not `IID` tek bir üye ile ilişkili olabilir. "Yalnızca bir en türetilmiş" bir arabirimi uyguluyor ve bu da tüm ara arabirimleri sağlamak istiyorsanız bu kullanışlıdır. Bunun iyi bir örnektir `IOleInPlaceFrameWindow` arabirimi. Hiyerarşi şöyle görünür:

```Hierarchy
IUnknown
    IOleWindow
        IOleUIWindow
            IOleInPlaceFrameWindow
```

Bir nesne uyguluyorsa `IOleInPlaceFrameWindow`, bir istemci `QueryInterface` şu arabirimlerin herhangi birinde bulunan: `IOleUIWindow`, `IOleWindow`, veya [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), "en türetilmiş" arabirim yanı sıra `IOleInPlaceFrameWindow` (aslında olduğunuz bir Uygulama). Bu durumu çözmek için birden fazla ınterface_part makrosu her bir taban arabirimi eşlemek için kullanabileceğiniz `IOleInPlaceFrameWindow` arabirimi:

sınıf tanımı dosyasında:

```cpp
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)
```

Sınıf uygulama dosyasında:

```cpp
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)
END_INTERFACE_MAP
```

Framework IUnknown her zaman gerekli olduğundan üstlenir.

### <a name="interfacepart--macro-description"></a>Interface_part — Makro tanımı

```cpp
INTERFACE_AGGREGATE(theClass, theAggr)
```

#### <a name="parameters"></a>Parametreler

*Sınıfın*  
Arabirim eşlemesini içeren sınıfın adı,

*theAggr*  
Toplanacak üye değişkeninin adı.

#### <a name="remarks"></a>Açıklamalar

Bu makro, framework sınıfın bir toplama nesnesi kullandığını söylemek için kullanılır. Bu, begın_ınterface_part ve end_ınterface_part makroları arasında yer almalıdır. Öğesinden türetilen ayrı bir nesne bir toplama nesnesi olduğu [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Toplama ve ınterface_aggregate makrosunu kullanarak, toplamanın desteklediği nesne tarafından doğrudan desteklenir gibi görünmesini tüm arabirimleri yapabilirsiniz. *TheAggr* yalnızca türetilmiş sınıfınızın bir üye değişkeninin adı olmayan bağımsız değişken [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) (doğrudan veya dolaylı olarak). Arabirim eşlemesine yerleştirildiğinde ınterface_part makroları tüm ınterface_aggregate makrolarını izlemelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)  
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)  
