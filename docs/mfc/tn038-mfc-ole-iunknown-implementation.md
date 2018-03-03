---
title: "TN038: MFC OLE IUnknown uygulaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a17ce210dffd13e0ffdac142c6121954eec1045d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn038-mfcole-iunknown-implementation"></a>TN038: MFC/OLE IUnknown Uygulaması
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 OLE 2 Kalp "OLE Bileşen Nesne modeli" veya COM değil COM tanımlayan bir standart nasıl birlikte çalışan nesneler için bir şekilde iletişim kurar. Bu yöntemler bir nesne üzerinde nasıl gönderilir dahil olmak üzere hangi bir "nesne" gibi görünür ayrıntılarını içerir. COM ayrıca tüm COM uyumlu sınıfları elde edilen bir taban sınıf tanımlar. Bu taban sınıf [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Ancak [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) arabirimi bir C++ sınıf olarak adlandırılır, COM herhangi bir dile özgü değildir — C, PASCAL veya bir COM nesnesi ikili düzenini destekleyen herhangi bir dil uygulanabilir.  
  
 Türetilen tüm sınıflar başvurduğu OLE [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) "arabirimler." Bu önemli bir fark "arabirimi" bu yana olduğu gibi [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ile uygulaması taşır. Yalnızca, olarak nesneleri iletişim, bu uygulamaları ne özellikleri değil protokol tanımlar. İçin en fazla esneklik sağlayan bir sistem için makul budur. MFC/C++ programları için varsayılan davranış uygulamak MFC'nin iş.  
  
 MFC'nin uyarlamasını anlamak için [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) bu arabirim nedir önce anlamanız gerekir. Basitleştirilmiş bir sürümünü [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) aşağıda tanımlanmıştır:  
  
```  
class IUnknown  
{  
public:  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;  
    virtual ULONG AddRef() = 0;  
    virtual ULONG Release() = 0;  
};  
```  
  
> [!NOTE]
>  Gibi belirli gerekli çağırma ayrıntıları `__stdcall` Bu çizim için sol.  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317) üye işlevleri denetleyen nesnenin bellek yönetimi. COM nesneleri izlemek için bir başvuru sayım düzenini kullanır. Nesne hiçbir zaman başvurulan c++'ta gibi doğrudan. Bunun yerine, COM nesneleri her zaman bir işaretçi başvurulur. Sahibi yapıldığında nesne serbest bırakmak için nesneyi 's kullanmaya [yayın](http://msdn.microsoft.com/library/windows/desktop/ms682317) üyesi (için geleneksel bir C++ nesnesi yapıldığı şekilde delete işleci, kullanarak aksine) çağrılır. Yönetilecek tek bir nesne için birden çok başvuru mekanizması sayım başvuru sağlar. Uygulaması [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317) nesne üzerinde bir başvuru sayımı tutar — başvuru sayısı sıfır ulaşana kadar nesne silinmez.  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317) bir uygulama açısından oldukça basittir. Önemsiz uygulama şöyledir:  
  
```  
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
  
 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) üye işlevi biraz daha ilginç. Bir nesnenin yalnızca, üye işlevleri sağlamak çok ilginç değil [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317) —'den daha fazla şeyler nesnesine bildirmek iyi [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) sağlar. Bu yerdir [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) yararlıdır. Farklı bir "arabirim" aynı nesne üzerinde elde imkan tanır. Bu arabirimleri genellikle türetilmiş [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ve yeni üye işlevleri ekleyerek ek işlevsellik ekleyin. COM arabirimleri hiçbir zaman arabirimde bildirilen değişkenlere sahiptir ve tüm üye işlevleri olarak sanal saf bildirilir. Örneğin,  
  
```  
class IPrintInterface : public IUnknown  
{  
public:  
    virtual void PrintObject() = 0;  
};  
```  
  
 Yalnızca varsa bir IPrintInterface almak için bir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), çağrı [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) kullanarak `IID` , **IPrintInterface**. Bir `IID` arabirimi benzersiz olarak tanımlayan bir 128-bit sayıdır. Var olan bir `IID` her arabirimin, veya OLE tanımlayın. Varsa `pUnk` gösteren bir işaretçidir bir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) nesnesi, bir IPrintInterface ondan almak için kodu olabilir:  
  
```  
IPrintInterface* pPrint = NULL;  
if (pUnk->QueryInterface(IID_IPrintInterface,   
 (void**)&pPrint) == NOERROR)  
{  
    pPrint->PrintObject();
pPrint->Release();
*// release pointer obtained via QueryInterface  
}  
```  
  
 Bu oldukça kolay görünüyor, ancak nasıl uygulayacağınıza hem IPrintInterface destekleyen bir nesne ve [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) arabirimi IPrintInterface doğrudan türetildiği beri bu durumda basittir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) — IPrintInterface, uygulama tarafından [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) otomatik olarak desteklenir. Örneğin:  
  
```  
class CPrintObj : public CPrintInterface  
{  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();
virtual void PrintObject();

};  
```  
  
 Uygulamaları [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317) tam olarak aynı bu uygulanan yukarıdaki olacaktır. **CPrintObj::QueryInterface** şunun gibi görünür:  
  
```  
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
  
 Arabirim tanımlayıcısı (IID) tanınırsa, gördüğünüz gibi bir işaretçi, nesnesine döndürülür; Aksi takdirde hata oluşur. Ayrıca başarılı bir [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) sonuçları bir kapsanan [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379). Elbette, CEditObj::Print uygulamak de gerekir. IPrintInterface doğrudan öğesinden türetilmiş çünkü basit olan [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) arabirimi. İki farklı arabirimleri desteklemek istiyorsanız, ancak her ikisi de türetilmiş [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), aşağıdakileri dikkate alın:  
  
```  
class IEditInterface : public IUnkown  
{  
public:  
    virtual void EditObject() = 0;  
};  
```  
  
 Birkaç farklı yolla IEditInterface ve C++ birden çok devralmayı kullanma dahil olmak üzere IPrintInterface destekleyen bir sınıf uygulama olsa Bu Not Bu işlevselliği uygulamak için iç içe geçmiş sınıflar kullanımını yoğunlaşabilirsiniz.  
  
```  
class CEditPrintObj  
{  
public:  
    CEditPrintObj();

 
    HRESULT QueryInterface(REFIID iid,
    void**);

    ULONG AddRef();
ULONG Release();
DWORD m_dwRef;  
 
    class CPrintObj : public IPrintInterface  
 {  
    public: 
    CEditPrintObj* m_pParent;  
    virtual HRESULT QueryInterface(REFIID iid,
    void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();

 } m_printObj;  
 
    class CEditObj : public IEditInterface  
 {  
    public: 
    CEditPrintObj* m_pParent;  
    virtual ULONG QueryInterface(REFIID iid,
    void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();

 } m_editObj;  
};  
```  
  
 Tüm uygulama aşağıda yer almaktadır:  
  
```  
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
 
HRESULT CEditPrintObj::QueryInterface(REFIID iid,
    void** ppvObj)  
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
 
HRESULT CEditPrintObj::CEditObj::QueryInterface(
    REFIID iid,
    void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid,
    ppvObj);

}  
 
ULONG CEditPrintObj::CPrintObj::AddRef()   
{   
    return m_pParent->AddRef();

}  
 
ULONG CEditPrintObj::CPrintObj::Release()   
{   
    return m_pParent->Release();

}  
 
HRESULT CEditPrintObj::CPrintObj::QueryInterface(
    REFIID iid,
    void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid,
    ppvObj);

}  
```  
  
 Çoğu fark [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) uygulama CEditPrintObj sınıfına yerleştirilir CEditPrintObj::CEditObj ve CEditPrintObj::CPrintObj kodda çoğaltmak yerine. Bu kod miktarını azaltır ve hataları önler. Anahtar burada IUnknown arabiriminden çağırmak mümkündür, noktasıdır [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) herhangi bir arabirim almak için nesne desteklemiyor olabilir ve her bu arabirimleri aynı yapmak mümkündür. Bunun anlamı tüm [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) her arabiriminden işlevleri tam olarak aynı şekilde davranır gerekir. "Dış nesne" uygulamasını çağırmak bu katıştırılmış nesneler için geri işaretçi kullanılan (m_pParent) sıradadır. M_pParent işaretçi sırasında CEditPrintObj Oluşturucusu başlatılır. Ardından CEditPrintObj::CPrintObj::PrintObject ve CEditPrintObj::CEditObj::EditObject de uygulamak. Bir özellik eklemek için oldukça biraz kod eklendi — nesne düzenleme özelliği. Neyse ki, yalnızca tek üye işlevi (durum rağmen) sahip arabirimler için oldukça seyrek olur ve bu durumda, EditObject ve PrintObject genellikle tek bir arabirim birleştirilmiş.  
  
 Açıklama çok ve çok basit bir senaryoyu kodunun olmasıdır. MFC/OLE sınıfları daha basit bir alternatif sunar. MFC uygulaması ileti eşlemeleri ile benzer şekilde Windows iletilerini kaydırılan bir teknik kullanır. Bu özellik adında *arabirimi eşlemeleri* ve sonraki bölümde açıklanmaktadır.  
  
## <a name="mfc-interface-maps"></a>MFC arabirimi eşlemeleri  
 MFC/OLE MFC'nin "İleti eşlemeleri" ve "Eşlemeleri dağıtma" benzer "arabirimi eşlemeleri" uygulaması kavram ve yürütme içerir. MFC'nin arabirimi eşlemeleri çekirdek özelliklerini aşağıdaki gibidir:  
  
-   Standart uygulaması [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), yerleşik `CCmdTarget` sınıfı.  
  
-   Bakım değiştiren başvuru sayısı [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) ve [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317)  
  
-   Veri uyarlamasını tabanlı [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)  
  
 Ayrıca, arabirim eşlemeleri gelişmiş özellikler aşağıdakileri destekler:  
  
-   Toplanabilir COM nesneleri oluşturma desteği  
  
-   Toplama nesneleri COM nesnesi uygulamasında kullanma desteği  
  
-   Uygulama hookable ve Genişletilebilir  
  
 Toplama hakkında daha fazla bilgi için bkz: [toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx) konu.  
  
 MFC'nin arabirimi harita desteği kökü `CCmdTarget` sınıfı. `CCmdTarget`"*sahip bir*" başvuru sayısı yanı sıra tüm üye işlevleri ilişkili [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) uygulaması (bulunduğu örneğin başvuru sayısı `CCmdTarget`). OLE COM destekleyen bir sınıf oluşturmak için öğesinden bir sınıf türetin `CCmdTarget` ve çeşitli makroları kullanma üye işlevlerinin yanı sıra `CCmdTarget` istenen arabirimlerini. MFC'nin uygulama iç içe geçmiş sınıflar her arabirim uygulamasına yukarıdaki örnekte olduğu gibi tanımlamak için kullanır. Bu, bazı yinelenen kodları ortadan makroları sayısı yanı sıra IUnknown standart bir uygulama ile daha kolay hale getirilmiştir.  
  
## <a name="interface-map-basics"></a>Harita temel arabirim  
  
#### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>MFC'nin arabirimini kullanarak bir sınıf uygulama eşlendiği  
  
1.  Doğrudan veya dolaylı bir öğesinden bir sınıf türetin `CCmdTarget`.  
  
2.  Kullanım `DECLARE_INTERFACE_MAP` türetilmiş sınıf tanımında işlevi.  
  
3.  Desteklemek istediğiniz her arabirim için kullanma `BEGIN_INTERFACE_PART` ve `END_INTERFACE_PART` makroları sınıf tanımında.  
  
4.  Uygulama dosyasında kullanmak `BEGIN_INTERFACE_MAP` ve `END_INTERFACE_MAP` sınıfın arabirim eşlemesi tanımlamak için makroları.  
  
5.  Desteklenen her IID için kullanmak `INTERFACE_PART` makrosu arasında `BEGIN_INTERFACE_MAP` ve `END_INTERFACE_MAP` belirli bir sınıfınızın "bölümünü" Bu IID eşlemek için makroları.  
  
6.  Her desteklediğiniz arabirimleri temsil eden iç içe geçmiş sınıflar uygulayın.  
  
7.  Kullanım `METHOD_PROLOGUE` üst erişmek için makrosu `CCmdTarget`-türetilmiş bir nesne içermelidir.  
  
8. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) için devredebilirsiniz `CCmdTarget` bu işlevlerin uygulaması (`ExternalAddRef`, `ExternalRelease`, ve `ExternalQueryInterface` ).  
  
 Yukarıdaki CPrintEditObj örnek gibi uygulanabilir:  
  
```  
class CPrintEditObj : public CCmdTarget  
{  
public: *// member data and member functions for CPrintEditObj go here  
 
// Interface Maps  
protected:  
    DECLARE_INTERFACE_MAP() 
 
    BEGIN_INTERFACE_PART(EditObj,
    IEditInterface)  
    STDMETHOD_(void,
    EditObject)();
END_INTERFACE_PART(EditObj) 
 
    BEGIN_INTERFACE_PART(PrintObj,
    IPrintInterface)  
    STDMETHOD_(void,
    PrintObject)();
END_INTERFACE_PART(PrintObj) 
};  
```  
  
 Yukarıdaki bildirimde türetilmiş bir sınıf oluşturur `CCmdTarget`. `DECLARE_INTERFACE_MAP` Makrosu framework Bu sınıf özel arabirim eşlemesi olduğunu bildirir. Ayrıca, `BEGIN_INTERFACE_PART` ve `END_INTERFACE_PART` makroları tanımlama iç içe geçmiş sınıflar, bu durumda adlarıyla CEditObj ve CPrintObj (X yalnızca iç içe geçmiş sınıflar "ı Başlat"C"ve arabirimi sınıflarını başlayın genel sınıflardan ayırt etmek için kullanılır "). Bu sınıfların iki iç içe üyesi oluşturulur: m_CEditObj ve m_CPrintObj, sırasıyla. Makrolar otomatik olarak bildirin [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) çalışır; bu nedenle, yalnızca işlevleri bu arabirime belirli bildirin: EditObject ve PrintObject (OLE makrosu `STDMETHOD` kullanılan böylece `_stdcall` ve sanal anahtar sözcükler hedef platformu için uygun şekilde sağlanır).  
  
 Bu sınıf için arabirim eşlemesi uygulamak için:  
  
```  
BEGIN_INTERFACE_MAP(CPrintEditObj,
    CCmdTarget)  
    INTERFACE_PART(CPrintEditObj,
    IID_IPrintInterface,
    PrintObj)  
    INTERFACE_PART(CPrintEditObj,
    IID_IEditInterface,
    EditObj)  
END_INTERFACE_MAP()  
```  
  
 Bu IID_IPrintInterface IID m_CPrintObj ve IID_IEditInterface ile m_CEditObj sırasıyla bağlar. `CCmdTarget` Uyarlamasını [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) (`CCmdTarget::ExternalQueryInterface`) m_CPrintObj ve istendiğinde m_CEditObj işaretçileri döndürmek için bu eşlemeyi kullanır. İçin bir giriş eklemek gerekli değildir `IID_IUnknown`; framework (Bu durumda, m_CPrintObj) eşlemesindeki ilk arabirimi zaman kullanacağı `IID_IUnknown` isteniyor.  
  
 Olsa bile `BEGIN_INTERFACE_PART` otomatik olarak bildirilen makrosu [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317) ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) işlevleri, hala uygulamadan vermeniz gerekir:  
  
```  
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return pThis->ExternalAddRef();

}  
 
ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return pThis->ExternalRelease();

}  
 
HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(
    REFIID iid,
    void FAR* FAR* ppvObj)  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return (HRESULT)pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
 
void FAR EXPORT CEditPrintObj::XEditObj::EditObject()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj) *// code to "Edit" the object,
    whatever that means...  
}  
```  
  
 CEditPrintObj::CPrintObj, uygulamasını olacaktır CEditPrintObj::CEditObj için yukarıdaki tanımları benzer. Bu işlevler otomatik olarak oluşturmak için kullanılabilecek bir makro oluşturmak mümkündür (ancak durum, önceki MFC/OLE geliştirme bu rağmen), bir makro birden fazla satır kod oluşturduğunda kesme noktası ayarlama zorlaşır. Bu nedenle, bu kodu el ile genişletilir.  
  
 İleti eşlemeleri framework uygulamasını kullanarak, pek çok yapmak için gereken bulunmayan vardır:  
  
-   QueryInterface uygulama  
  
-   Uygulama AddRef ve sürüm  
  
-   Bu yerleşik yöntemlerden birini hem arabirimlerinizin bildirme  
  
 Ayrıca, çerçeve ileti eşlemeleri dahili olarak kullanılır. Bu sayede deyin framework sınıfından türetilen `COleServerDoc`, zaten belirli arabirimleri destekler ve değişiklik veya eklemeler çerçevesi tarafından sağlanan arabirimleri sağlar. Framework tam olarak bir arabirim eşlemesi temel sınıfından devralan desteklediği için bunu yapabilirsiniz. Bunun nedeni neden olan `BEGIN_INTERFACE_MAP` , ikinci parametre olarak temel sınıfın adını alır.  
  
> [!NOTE]
>  Genelde bu arabirimin katıştırılmış uzmanlık yalnızca MFC sürümünden devralarak MFC'nin yerleşik uygulamaları OLE arabirimleri uyarlamasını yeniden mümkün değildir. Bu mümkün değildir çünkü kullanımını `METHOD_PROLOGUE` içeren erişmek için makrosu `CCmdTarget`-türetilen nesne gelir bir *Sabit uzaklık* katıştırılmış nesne, `CCmdTarget`-nesne türetilmiş. Bu, örneğin, size olamaz türetilen katıştırılmış XMyAdviseSink MFC'nin uygulamasında anlamına gelir `COleClientItem::XAdviseSink`XAdviseSink üstünden belirli uzaklığındaki dayanır çünkü `COleClientItem` nesnesi.  
  
> [!NOTE]
>  Ancak, tüm MFC'ın varsayılan davranışı istediğiniz işlevleri için MFC uygulaması için temsilci olabilir. Bu MFC uygulaması yapılır `IOleInPlaceFrame` (XOleInPlaceFrame) içinde `COleFrameHook` sınıfı (bunu temsilciler birçok işlevini m_xOleInPlaceUIWindow için). Bu tasarım, birçok arabirimleri uygulayan nesneler çalışma zamanı boyutunu azaltmak için seçildi; (önceki bölümde şekilde m_pParent kullanılan gibi) geri işaretçi gereksinimini ortadan kaldırır.  
  
### <a name="aggregation-and-interface-maps"></a>Toplama ve arabirim eşlemeleri  
 Tek başına COM nesneleri'ı desteklemenin yanında MFC toplama de destekler. Toplama kendisini burada tartışmak için çok karmaşık bir konudur; başvurmak [toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx) toplama hakkında daha fazla bilgi için konu. Bu not yalnızca toplama framework ve arabirim eşlemeleri yerleşik desteği anlatmaktadır.  
  
 Toplama kullanmanın iki yolu vardır: (1) toplama destekleyen bir COM nesnesi kullanılarak ve (2) bir başkası tarafından toplanan nesneyi uygulama. Bu özellikler "toplama bir nesne kullanarak" ve "bir nesne toplanabilir yaparak" olarak başvuruda bulunulabilir. MFC her ikisi de destekler.  
  
### <a name="using-an-aggregate-object"></a>Toplama bir nesne kullanma  
 QueryInterface mekanizması içine toplama bağlamanın bir şekilde olması gerekiyor var. toplama bir nesne kullanmak için. Nesnenizin yerel bir parçası olduğu gibi diğer bir deyişle, toplama bir nesne davranır gerekir. Nasıl bu bağ MFC'nin arabirimi içine eşleme mekanizması ek olarak `INTERFACE_PART` makrosu, iç içe nesne bir IID için eşlenen burada da bildirebilirsiniz toplama bir nesne bir parçası olarak, `CCmdTarget` türetilmiş sınıf. Bunu yapmak için `INTERFACE_AGGREGATE` makrosu kullanılır. Bu üye değişkeni belirtmenize olanak tanır (bir işaretçi olması gerekir bir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) veya türetilmiş sınıf), arabirim harita mekanizmasına tümleşik olduğu. İşaretçinin ne zaman NULL değilse `CCmdTarget::ExternalQueryInterface` olduğu adlı framework otomatik olarak birleşik nesnenin çağıracak [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) üye işlev, varsa `IID` istenen biri yerel değil `IID`s tarafından desteklenen `CCmdTarget` nesnesinin kendisi.  
  
##### <a name="to-use-the-interfaceaggregate-macro"></a>INTERFACE_AGGREGATE makrosu kullanmak için  
  
1.  Üye değişkeni bildirme (bir `IUnknown*`) toplama bir nesne için bir işaretçi içerecek.  
  
2.  Dahil bir `INTERFACE_AGGREGATE` makrosu adıyla üye değişkenine başvuruyor, eşlemesindeki arabirimi.  
  
3.  Belirli bir noktada (genellikle sırasında `CCmdTarget::OnCreateAggregates`), NULL dışında bir şey için üye değişkeni başlatılamıyor.  
  
 Örneğin:  
  
```  
class CAggrExample : public CCmdTarget  
{  
public:  
    CAggrExample();

 
protected:  
    LPUNKNOWN m_lpAggrInner;  
    virtual BOOL OnCreateAggregates();

 
    DECLARE_INTERFACE_MAP() *// "native" interface part macros may be used here  
};  
 
CAggrExample::CAggrExample()  
{  
    m_lpAggrInner = NULL;  
}  
 
BOOL CAggrExample::OnCreateAggregates()  
{ *// wire up aggregate with correct controlling unknown  
    m_lpAggrInner = CoCreateInstance(CLSID_Example,  
    GetControllingUnknown(),
    CLSCTX_INPROC_SERVER,  
    IID_IUnknown, (LPVOID*)&m_lpAggrInner);

    if (m_lpAggrInner == NULL)  
    return FALSE; *// optionally,
    create other aggregate objects here  
    return TRUE;  
}  
 
BEGIN_INTERFACE_MAP(CAggrExample,
    CCmdTarget) *// native "INTERFACE_PART" entries go here  
    INTERFACE_AGGREGATE(CAggrExample,
    m_lpAggrInner)  
END_INTERFACE_MAP()  
```  
  
 M_lpAggrInner değişkeni null oluşturucuda başlatılır. Framework varsayılan uygulaması bir NULL üye değişkeni yok sayıyor [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). `OnCreateAggregates`Aslında, toplama nesneleri oluşturmak için uygun bir yerdir. MFC uygulaması dışında nesne oluşturuyorsanız açıkça çağırın gerekecek `COleObjectFactory`. Toplamaların oluşturma nedenini `CCmdTarget::OnCreateAggregates` kullanımını yanı sıra `CCmdTarget::GetControllingUnknown` toplanabilir nesneleri oluşturma açıklanan zaman görünür olur.  
  
 Bu teknik nesnenizin tüm yerel arabirimlerinden toplama bir nesne destekleyen arabirimleri sunar. Yalnızca bir alt toplam destekleyen arabirimlerin istiyorsanız, geçersiz kılabilirsiniz `CCmdTarget::GetInterfaceHook`. Çok düşük düzeyli hookability, benzer şekilde bu sayede [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521). Genellikle, toplama destekleyen tüm arabirimler istiyor.  
  
### <a name="making-an-object-implementation-aggregatable"></a>Nesne uygulaması toplanabilir yapma  
 Toplanabilir, olması bir nesne uygulanması için [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) bir "denetleme bilinmeyen olarak." temsilci gerekir Diğer bir deyişle, bu nesnenin parçası olarak temsilci gerekir [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) farklı bir nesneye de türetilmiş [ IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Bu "denetleme bilinmiyor" oluşturulduğunda, nesneyi başka bir deyişle, onu uygulanması için sağlanan sağlanır `COleObjectFactory`. Bu uygulama yükünü az miktarda gerçekleştirir ve MFC bu isteğe bağlı hale şekilde bazı durumlarda arzu, değil. Toplanabilir olması için bir nesne etkinleştirmek için arama `CCmdTarget::EnableAggregation` nesnenin oluşturucusundan.  
  
 Nesne aynı zamanda toplamalar kullanıyorsa, ayrıca doğru aktardığınızdan emin olmalısınız toplama nesneleri için "denetleme bilinmiyor". Genellikle bu [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) toplama oluşturulduğunda işaretçi nesneye iletilir. Örneğin, pUnkOuter parametresi "denetleme" ile oluşturulan nesneler için bilinmiyor `CoCreateInstance`. "Bilinmeyen denetleme" doğru işaretçiyi çağırarak alınabilir `CCmdTarget::GetControllingUnknown`. Bu işlevinden döndürülen değer ancak sırasında Oluşturucusu geçerli değil. Bu nedenle, yalnızca geçersiz kılma içinde toplamaları oluşturun önerilir `CCmdTarget::OnCreateAggregates`, dönüş değeri burada `GetControllingUnknown` oluşturulan olsa bile güvenilirdir `COleObjectFactory` uygulaması.  
  
 Nesne eklerken veya yapay başvuru sayıları serbest doğru başvuru sayısı işlemek önemlidir. Bu durumda olduğundan emin olmak için her zaman çağrısı `ExternalAddRef` ve `ExternalRelease` yerine `InternalRelease` ve `InternalAddRef`. Çağrılacak nadir `InternalRelease` veya `InternalAddRef` toplama destekleyen bir sınıf.  
  
### <a name="reference-material"></a>Başvuru bilgileri  
 Kendi arabirimleri tanımlama veya OLE arabirimleri framework'ün uygulamasını geçersiz kılma gibi OLE, Gelişmiş kullanımını temel arabirimi eşleme mekanizmasını kullanılmasını gerektirir.  
  
 Bu bölümde her makrosu ve bu Gelişmiş Özellikler uygulamak için kullanılan API'leri anlatılmaktadır.  
  
### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget::EnableAggregation — İşlevi açıklaması  
  
```  
 
void EnableAggregation();

 
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu tür nesneler için OLE toplama desteklemek istiyorsanız, bu işlevi türetilmiş sınıf oluşturucu çağırın. Toplanabilir nesneler için gerekli olan özel bir IUnknown uygulaması hazırlar.  
  
### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget::ExternalQueryInterface — İşlevi açıklaması  
  
```  
 
    DWORD ExternalQueryInterface(constvoidFAR* lpIID, LPVOIDFAR* ppvObj);
```  
  
## <a name="remarks"></a>Açıklamalar  
  
#### <a name="parameters"></a>Parametreler  
 `lpIID`  
 Bir IID (ilk bağımsız değişkeni için QueryInterface) kadar bir işaretçi  
  
 `ppvObj`  
 Bir işaretçi bir IUnknown * (ikinci bağımsız değişkeni için QueryInterface)  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev IUnknown uygulamanızda her arabirim için sınıfınız çağrısı uygular. Bu işlev, nesnenin arabirimi haritada dayalı QueryInterface standart verilere uygulamasını sağlar. HRESULT dönüş değerini dönüştürmek gereklidir. Nesne toplanır, bu işlev "IUnknown" yerel arabirim eşlemesi kullanmak yerine çağırır.  
  
### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget::ExternalAddRef — İşlevi açıklaması  
  
```  
 
DWORD ExternalAddRef();

 
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev IUnknown::AddRef uygulamanızda her arabirim için sınıfınız çağrısı uygular. Dönüş değeri CCmdTarget nesne üzerinde yeni başvuru sayı değil. Nesne toplanır, bu işlev "IUnknown" yerel başvuru sayısı düzenleme yerine çağırır.  
  
### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget::ExternalRelease — İşlevi açıklaması  
  
```  
 
DWORD ExternalRelease();

 
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev IUnknown::Release uygulamanızda her arabirim için sınıfınız çağrısı uygular. Dönüş değeri nesne üzerinde yeni başvuru sayısını gösterir. Nesne toplanır, bu işlev "IUnknown" yerel başvuru sayısı düzenleme yerine çağırır.  
  
### <a name="declareinterfacemap--macro-description"></a>Declare_ınterface_map — Makrosu açıklaması  
  
```  
 
DECLARE_INTERFACE_MAP  
 
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu türetilen sınıfı kullanın `CCmdTarget` bir arabirim eşlemesi olacaktır. Benzer şekilde kullanılan `DECLARE_MESSAGE_MAP`. Bu makrosu çağırma sınıf tanımında, genellikle bir üstbilgi yerleştirilmelidir (. H) dosyası. Bir sınıfla `DECLARE_INTERFACE_MAP` arabirim eşlemesi uygulama dosyada tanımlamanız gerekir (. CPP) ile `BEGIN_INTERFACE_MAP` ve `END_INTERFACE_MAP` makroları.  
  
### <a name="begininterfacepart-and-endinterfacepart--macro-descriptions"></a>Begın_ınterface_part ve end_ınterface_part — makrosu açıklamaları  
  
```  
 
    BEGIN_INTERFACE_PART(
 localClass,   
    iface);

END_INTERFACE_PART(
 localClass)  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
#### <a name="parameters"></a>Parametreler  
 `localClass`  
 Arabirimini uygulayan sınıf adı  
  
 `iface`  
 Bu sınıf uygulayan arabirim adı  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfınıza gerçekleştireceksiniz her arabirim için olması gerekir. bir `BEGIN_INTERFACE_PART` ve `END_INTERFACE_PART` çifti. Bu makroları yanı sıra bu sınıfın bir katıştırılmış üye değişkeni tanımlamanız OLE arabirimi türetilmiş yerel bir sınıfı tanımlar. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [sürüm](http://msdn.microsoft.com/library/windows/desktop/ms682317), ve [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) üyeleri otomatik olarak bildirildiğinde. Uygulanan arabirimi parçası olan bir üye işlevleri için bildirimleri eklemeniz gerekir (Bu bildirimleri intranetiniz arasında `BEGIN_INTERFACE_PART` ve `END_INTERFACE_PART` makroları).  
  
 `iface` Bağımsız değişkeni olduğu gibi uygulamak istediğiniz OLE arabirimi `IAdviseSink`, veya `IPersistStorage` (veya kendi özel arabirim).  
  
 `localClass` Bağımsız değişkeni tanımlanacağı yerel sınıfı adıdır. Bir'X ' adına $a otomatik olarak. Bu adlandırma kuralını aynı ada sahip genel sınıflarla çakışmaları önlemek için kullanılır. Ayrıca, katıştırılmış üyenin adını, aynı `localClass` 'm_x tarafından' öneki dışında adı.  
  
 Örneğin:  
  
```  
BEGIN_INTERFACE_PART(MyAdviseSink,
    IAdviseSink)  
    STDMETHOD_(void,
    OnDataChange)(LPFORMATETC,
    LPSTGMEDIUM);

    STDMETHOD_(void,
    OnViewChange)(DWORD,
    LONG);

    STDMETHOD_(void,
    OnRename)(LPMONIKER);

 STDMETHOD_(void,
    OnSave)();
STDMETHOD_(void,
    OnClose)();

END_INTERFACE_PART(MyAdviseSink) 
```  
  
 IAdviseSink türetilen XMyAdviseSink adlı yerel bir sınıf tanımlamanız gerekir ve içinde bildirilmiş sınıf üyesi m_xMyAdviseSink.Note çağrılır:  
  
> [!NOTE]
>  İle başlayan satırlar `STDMETHOD`_ OLE2 temelde kopyalanır. H ve biraz değiştirilmiş. Bunları OLE2 kopyalanıyor. H çözümlemek sabit hataları azaltabilir.  
  
### <a name="begininterfacemap-and-endinterfacemap--macro-descriptions"></a>Begın_ınterface_map ve end_ınterface_map — makrosu açıklamaları  
  
```  
 
    BEGIN_INTERFACE_MAP(
 theClass,   
    baseClass)END_INTERFACE_MAP 
```  
  
## <a name="remarks"></a>Açıklamalar  
  
#### <a name="parameters"></a>Parametreler  
 `theClass`  
 Arabirim eşlemesi tanımlanacak olduğu sınıfı  
  
 `baseClass`  
 Sınıfından `theClass` türetir.  
  
## <a name="remarks"></a>Açıklamalar  
 `BEGIN_INTERFACE_MAP` Ve `END_INTERFACE_MAP` makroları uygulama dosyasında gerçekten arabirim eşlemesi tanımlamak için kullanılır. Uygulanan her arabirim için var olan bir veya daha fazla `INTERFACE_PART` makrosu çağrılarını. Sınıfını kullanan her toplama için bir olduğundan `INTERFACE_AGGREGATE` makrosu çağırma.  
  
### <a name="interfacepart--macro-description"></a>Interface_part — Makrosu açıklaması  
  
```  
 
    INTERFACE_PART(
 theClass,   
    iid, 
    localClass) 
```  
  
## <a name="remarks"></a>Açıklamalar  
  
#### <a name="parameters"></a>Parametreler  
 `theClass`  
 Arabirim eşlemesi içeren sınıfın adı.  
  
 `iid`  
 `IID` Olan katıştırılmış sınıfına eşlenemez.  
  
 `localClass`  
 (Daha az ' X') yerel sınıfın adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu arasında kullanılan `BEGIN_INTERFACE_MAP` makrosu ve `END_INTERFACE_MAP` nesnenizin makrosu her arabirim için destekler. Belirtilen sınıf üyesi için bir IID eşlemenizi sağlar `theClass` ve `localClass`. 'm_x' eklenecek `localClass` otomatik olarak. Not birden fazla `IID` tek bir üye ile ilişkili olabilir. Yalnızca bir "en türetilmiş" arabirimini uygulayan ve tüm ara arabirimleri de sağlamak istiyorsanız bu oldukça yararlıdır. Bu iyi bir örnektir `IOleInPlaceFrameWindow` arabirimi. Hiyerarşisi şöyle görünür:  
  
```  
IUnknown  
    IOleWindow 
    IOleUIWindow 
    IOleInPlaceFrameWindow 
```  
  
 Bir nesne uyguluyorsa `IOleInPlaceFrameWindow`, bir istemci olabilir `QueryInterface` bu arabirimleri hiçbirinde: `IOleUIWindow`, `IOleWindow`, veya [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), "en çok türetilen" arabirimi yanı sıra `IOleInPlaceFrameWindow` (gerçekten olduğunuz bir Uygulama). Bu durumu çözmek için birden fazla kullanabilirsiniz `INTERFACE_PART` her temel arabirimine eşlemek için makrosu `IOleInPlaceFrameWindow` arabirimi:  
  
 sınıf tanımı dosyasında:  
  
```  
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)  
```  
  
 Sınıf uygulama dosyasında:  
  
```  
BEGIN_INTERFACE_MAP(CMyWnd,
    CFrameWnd)  
    INTERFACE_PART(CMyWnd,
    IID_IOleWindow,
    MyFrameWindow)  
    INTERFACE_PART(CMyWnd,
    IID_IOleUIWindow,
    MyFrameWindow)  
    INTERFACE_PART(CMyWnd,
    IID_IOleInPlaceFrameWindow,
    MyFrameWindow)  
END_INTERFACE_MAP  
```  
  
 Framework alır, her zaman gerekli olduğundan IUnknown olur.  
  
### <a name="interfacepart--macro-description"></a>Interface_part — Makrosu açıklaması  
  
```  
 
    INTERFACE_AGGREGATE(
 theClass,   
    theAggr) 
```  
  
## <a name="remarks"></a>Açıklamalar  
  
#### <a name="parameters"></a>Parametreler  
 `theClass`  
 Arabirim eşlemesi içeren sınıf adı,  
  
 `theAggr`  
 Toplanacak olan üye değişkeni adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu makrosu framework toplama bir nesne sınıfını kullanarak olduğunu bildirmek için kullanılır. Arasında görünmelidir `BEGIN_INTERFACE_PART` ve `END_INTERFACE_PART` makroları. Türetilen ayrı bir nesne bir toplama nesnedir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509). Bir toplama kullanarak ve `INTERFACE_AGGREGATE` makrosu, nesne tarafından doğrudan desteklenecek toplama destekler görünür tüm arabirimler yapabilir. `theAggr` Bağımsız değişkeni olan yalnızca bir üye değişkenine sınıfından türetilmiş sınıfının adını [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) (doğrudan veya dolaylı olarak). Tüm `INTERFACE_AGGREGATE` makroları uymalıdır `INTERFACE_PART` bir arabirim eşlemesi yerleştirildiğinde makroları.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

