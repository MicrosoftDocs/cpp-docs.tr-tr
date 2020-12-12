---
description: 'Daha fazla bilgi edinin: taşıma Kılavuzu: COM Spy'
title: 'Taşıma Kılavuzu: COM Spy'
ms.date: 11/04/2016
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
ms.openlocfilehash: 69a97a04d255e64fdde0d863e637d72dfb238967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322652"
---
# <a name="porting-guide-com-spy"></a>Taşıma Kılavuzu: COM Spy

Bu konu, eski Visual Studio C++ projelerini Visual Studio 'nun en son sürümüne yükseltme sürecini gösteren bir dizi makalede ikinci sürümdür. Bu konudaki örnek kod, en son Visual Studio 2005 ile derlendi.

## <a name="comspy"></a>COMSpy

COMSpy, bir makinede servis verilen bileşenlerin etkinliklerini izleyen ve kaydeden bir programdır. Hizmet verilen bileşenler, bir sistemde çalışan ve aynı ağdaki bilgisayarlar tarafından kullanılabilen COM+ bileşenleridir. Bunlar, Windows Denetim Masası 'ndaki Bileşen Hizmetleri işlevselliği tarafından yönetilirler.

### <a name="step-1-converting-the-project-file"></a>Adım 1. Proje dosyası dönüştürülüyor

Proje dosyası kolayca dönüştürülür ve bir geçiş raporu oluşturur. Raporda, ilgilenmemiz gerekebilecek sorunlar hakkında bize izin veren birkaç giriş vardır. Bildirilen bir sorun aşağıda verilmiştir (Bu konuda, hata iletilerinin bazen okunabilirlik için kısaltıldığına, örneğin tam yolları kaldırmasına) izin verilmiştir:

```Output
ComSpyAudit\ComSpyAudit.vcproj: MSB8012: $(TargetPath) ('C:\Users\UserName\Desktop\spy\spy\ComSpyAudit\.\XP32_DEBUG\ComSpyAudit.dll') does not match the Librarian's OutputFile property value '.\XP32_DEBUG\ComSpyAudit.dll' ('C:\Users\UserName\Desktop\spy\spy\XP32_DEBUG\ComSpyAudit.dll') in project configuration 'Unicode Debug|Win32'. This may cause your project to build incorrectly. To correct this, please make sure that $(TargetPath) property value matches the value specified in %(Lib.OutputFile).
```

Projeleri yükseltmekte olan sık karşılaşılan sorunlardan biri, proje özellikleri iletişim kutusundaki **bağlayıcı ÇıktıDosyası** ayarının gözden geçirilmesi gerekebilir. Visual Studio 2010 öncesi projeler için, ÇıktıDosyası standart olmayan bir değere ayarlanmışsa otomatik dönüştürme sihirbazının ile ilgili sorun sahip olduğu bir ayardır. Bu durumda, çıkış dosyalarının yolları standart olmayan bir klasöre ayarlanmıştır, XP32_DEBUG. Bu hatayla ilgili daha fazla bilgi edinmek için, VCBuild 'dan MSBuild 'e yapılan değişikliği içeren yükseltme, önemli bir değişiklik olan Visual Studio 2010 proje yükseltmesine ilişkin bir [blog gönderisi](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/) yaptık. Bu bilgilere göre, yeni bir proje oluşturduğunuz zaman **Çıkış dosyası** ayarı için varsayılan değer, `$(OutDir)$(TargetName)$(TargetExt)` ancak dönüştürme sırasında, her şeyin doğru olduğunu doğrulamak için dönüştürülen projeler mümkün olmadığından bu şekilde ayarlanamaz. Bununla birlikte, bunu ÇıktıDosyası için ' de almayı deneyelim ve çalışıp çalışmadığını görelim.  Böylece, üzerinde geçiş yapabilirsiniz. Standart olmayan çıkış klasörü kullanmanın belirli bir nedeni yoksa, standart konumu kullanmanızı öneririz. Bu durumda, taşıma ve yükseltme işlemi sırasında çıkış konumunu standart olmayan olarak bırakmayı seçtik; , `$(OutDir)` **Sürüm** yapılandırmasının **hata ayıklama** yapılandırmasındaki XP32_DEBUG klasörüne ve ReleaseU klasörüne çözümler.

### <a name="step-2-getting-it-to-build"></a>Adım 2. Oluşturmaya alma

Bağlantı noktası verilen projeyi oluşturma, bir dizi hata ve uyarı meydana gelir.

`ComSpyCtl` Bu derleyici hatası nedeniyle, derleme yapmaz:

```Output
atlcom.h(611): error C2664: 'HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM,BOOL,ATL::ATL_PROPMAP_ENTRY *)': cannot convert argument 3 from 'const ATL::ATL_PROPMAP_ENTRY *' to 'ATL::ATL_PROPMAP_ENTRY *'atlcom.h(611): note: Conversion loses qualifiersatlcom.h(608): note: while compiling class template member function 'HRESULT ATL::IPersistStreamInitImpl<CComSpy>::Save(LPSTREAM,BOOL)'\spy\spy\comspyctl\ccomspy.h(28): note: see reference to class template instantiation 'ATL::IPersistStreamInitImpl<CComSpy>' being compiled
```

Hata, `Save` `IPersistStreamInitImpl` atlcom. h içindeki sınıfında bulunan yöntemine başvurur.

```cpp
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)
{
     T* pT = static_cast<T*>(this);
     ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));
     return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());
}
```

Bu sorun, derleyicinin daha eski bir sürümünün kabul edildiği bir dönüştürmenin artık geçerli olmadığı bir dönüştürmedir. C++ standardına uygun olması için, daha önce izin verilen bazı koda artık izin verilmez. Bu durumda, const olmayan bir işaretçiyi const işaretçisi bekleyen bir işleve geçirmek güvenli değildir.  Çözüm, sınıfının bildirimini bulmak `IPersistStreamInit_Save` `CComSpy` ve üçüncü parametreye const değiştiricisini eklemektir.

```cpp
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)
```

Ve buna benzer bir değişiklik `IPersistStreamInit_Load` .

```cpp
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);
```

Sonraki hata kayıt ile ilgilidir.

```Output
error MSB3073: The command "regsvr32 /s /c "C:\Users\username\Desktop\spy\spy\ComSpyCtl\.\XP32_DEBUG\ComSpyCtl.lib"error MSB3073: echo regsvr32 exec. time > ".\XP32_DEBUG\regsvr32.trg"error MSB3073:error MSB3073: :VCEnd" exited with code 3.
```

Bu derleme sonrası kayıt komutuna artık gerek duymuyoruz. Bunun yerine, Özel Yapı komutunu kaldırdık ve çıktının kaydedileceği **bağlayıcı** ayarlarında belirtmeniz yeterlidir.

### <a name="dealing-with-warnings"></a>Uyarılarla ilgilenme

Proje aşağıdaki bağlayıcı uyarısını üretir.

```Output
warning LNK4075: ignoring '/EDITANDCONTINUE' due to '/SAFESEH' specification
```

`/SAFESEH`Derleyici seçeneği, yararlı olduğu durumlarda hata ayıklama modunda yararlı değildir, bu `/EDITANDCONTINUE` nedenle buradaki düzeltmeler `/SAFESEH` yalnızca **hata ayıklama** yapılandırması için devre dışı bırakılır. Özellik iletişim kutusunda bunu yapmak için, bu hatayı üreten projenin özellik iletişim kutusunu açar ve önce **yapılandırmayı** **Hata Ayıkla** (aslında **Unicode Hata Ayıkla**) olarak ayarlayacağız ve sonra **bağlayıcı gelişmiş** bölümünde, **görüntüde güvenli özel durum işleyicileri** özelliği () **yok** olarak ayarlanır `/SAFESEH:NO` .

Derleyici, kullanım dışı bırakılan bizi uyarır `PROP_ENTRY_EX` . Bu güvenli değildir ve önerilen alternatifi `PROP_ENTRY_TYPE_EX` .

```cpp
BEGIN_PROPERTY_MAP(CComSpy)
     PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_PAGE(CLSID_StockFontPage)
END_PROPERTY_MAP()
```

CComSpy. h içindeki kodu uygun şekilde değiştirin.

```cpp
BEGIN_PROPERTY_MAP(CComSpy)
     PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)
     PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)
     PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)
     PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)
     PROP_PAGE(CLSID_StockFontPage)
END_PROPERTY_MAP()
```

Daha sıkı derleyici uyumluluk denetimlerinden kaynaklanan en son birkaç uyarıyı inceleyeceğiz:

```Output
\spy\comspyctl\usersub.h(70): warning C4457: declaration of 'var' hides function parameter\spy\comspyctl\usersub.h(48): note: see declaration of 'var'\spy\comspyctl\usersub.h(94): warning C4018: '<': signed/unsigned mismatch  ComSpy.cpp\spy\comspyctl\comspy.cpp(186): warning C4457: declaration of 'bHandled' hides function parameter\spy\spy\comspyctl\comspy.cpp(177): note: see declaration of 'bHandled'
```

Uyarı C4018 şu koddan geliyor:

```cpp
for (i=0;i<lCount;i++)
    CoTaskMemFree(pKeys[i]);
```

Bu sorun olarak bildirildiği `i` `UINT` ve `lCount` olarak bildirildiği **`long`** , bu nedenle imzalı/imzasız uyuşmazlığı. Türünü `lCount` `UINT` `IMtsEventInfo::get_Count` kullandığından **`long`** ve Kullanıcı kodunda değil, ' ın değerini aldığından, türünün olarak değiştirilmesi yararlı olacaktır. Bu nedenle koda bir tür dönüştürme ekleyeceğiz. C stili bir tür dönüştürme, bu gibi sayısal bir atama için yapılır, ancak **`static_cast`** Önerilen stildir.

```cpp
for (i=0;i<static_cast<UINT>(lCount);i++)
    CoTaskMemFree(pKeys[i]);
```

Bu uyarılar, bir değişkenin aynı ada sahip bir parametreye sahip bir işlevde bildirildiği, önde gelen ve potansiyel olarak karmaşık kod olduğu durumlardır. Yerel değişkenlerin adlarını değiştirerek bunu düzelttik.

### <a name="step-3-testing-and-debugging"></a>3. Adım Test etme ve hata ayıklama

Uygulamayı, çeşitli menüler ve komutlar aracılığıyla çalıştırıp uygulamayı kapatarak test ederiz. Belirtilen tek sorun, uygulamanın kapatılması sırasında hata ayıklama onaylandı. Sorun, için yok edicinin, `CWindowImpl` `CSpyCon` UYGULAMANıN ana com bileşeni olan nesnenin temel sınıfı. Atlwin. h içinde aşağıdaki kodda onaylama işlemi hatası oluştu.

```cpp
virtual ~CWindowImplRoot()
{
     #ifdef _DEBUG
     if(m_hWnd != NULL)// should be cleared in WindowProc
     {
          ATLTRACE(atlTraceWindowing, 0, _T("ERROR - Object deleted before window was destroyed\n"));
          ATLASSERT(FALSE);
     }
     #endif //_DEBUG
}
```

`hWnd`Normalde işlevde sıfır olarak ayarlanır `WindowProc` , ancak varsayılan yerine `WindowProc` , pencereyi kapatan Windows iletisi (WM_SYSCOMMAND) için özel bir işleyici çağırılır. Özel işleyici öğesini sıfır olarak ayarlamamıştı `hWnd` . MFC sınıfında benzer koda göz atın `CWnd` , bir pencere yok edildiğinde, `OnNcDestroy` ÇAĞRıLDıĞıNDA ve MFC 'de, geçersiz kılınırken `CWnd::OnNcDestroy` `NcDestroy` pencere tanıtıcısını ayırmak, diğer bir deyişle, sıfır olarak ayarlamak dahil olmak üzere, doğru temizleme işlemlerinin meydana geldiğinden emin olmak için tabanın çağrılması gerektiğini gösterir `hWnd` . Aynı onaylama kodu, atlwin. h 'nin eski sürümünde bulunduğundan, bu onay örnek orijinal sürümünde de tetiklenebilir.

Uygulamanın işlevselliğini test etmek için ATL Proje şablonunu kullanarak **hizmet verilen bir bileşen** oluşturduk, ATL Proje SIHIRBAZı 'nda com+ desteği eklemeyi seçtiniz. Önceden servise alınmış bileşenlerle daha önce çalışmadıysanız, bir tane oluşturmak ve diğer uygulamaların kullanması için sistemde veya ağda kayıtlı ve kullanılabilir hale getirmek zor değildir. COM Spy uygulaması, hizmet verilen bileşenlerin etkinliğini bir tanılama Yardımcısı olarak izlemek için tasarlanmıştır.

Daha sonra bir sınıf ekledik, ATL nesnesi seçtik ve nesne adını olarak belirttik `Dog` . Ardından, köpek. h ve köpek. cpp içinde uygulamayı ekledik.

```cpp
STDMETHODIMP CDog::Wag(LONG* lDuration)
{
    // TODO: Add your implementation code here
    *lDuration = 100l;
    return S_OK;
}
```

Daha sonra, (Visual Studio 'Yu yönetici olarak çalıştırmanız gerekir) ve Windows Denetim Masası 'ndaki **hizmet verilen bileşen** uygulamasını kullanarak etkinleştiriyoruz. Bir C# Windows Forms projesi oluşturdunuz, araç kutusundan forma sürükliyoruz ve bir Click olay işleyicisine çift tıkladık. Bileşeni oluşturmak için aşağıdaki kodu ekledik `Dog` .

```cpp
private void button1_Click(object sender, EventArgs e)
{
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();
    dog1.Wag();
}
```

Bu, sorunsuz bir şekilde çalışır ve COM Spy ile çalışmaya çalışır ve bileşeni izlemek için yapılandırılır ve bu da, `Dog` etkinliği gösteren çok sayıda veri görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Sonraki örnek: Spy + +](../porting/porting-guide-spy-increment.md)<br/>
[Önceki örnek: MFC karalama](../porting/porting-guide-mfc-scribble.md)
