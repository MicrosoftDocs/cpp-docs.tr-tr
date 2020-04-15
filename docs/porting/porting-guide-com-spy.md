---
title: 'Taşıma Kılavuzu: COM Spy'
ms.date: 11/04/2016
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
ms.openlocfilehash: f4fece07b9ea4541d8bf21dd81fd659b44f39718
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368455"
---
# <a name="porting-guide-com-spy"></a>Taşıma Kılavuzu: COM Spy

Bu konu, eski Visual Studio C++ projelerini Visual Studio'nun en son sürümüne yükseltme işlemini gösteren bir dizi makalenin ikincisidir. Bu konudaki örnek kod en son Visual Studio 2005 ile derlenmiştir.

## <a name="comspy"></a>KOMSpy

COMSpy bir makinede servis edilen bileşenlerin etkinliğini izleyen ve kaydeden bir programdır. Servis edilen bileşenler, bir sistemde çalışan ve aynı ağdaki bilgisayarlar tarafından kullanılabilen COM+ bileşenleridir. Windows Denetim Masası'ndaki Bileşen Hizmetleri işlevleri tarafından yönetilirler.

### <a name="step-1-converting-the-project-file"></a>1. Adım. Proje dosyasını dönüştürme

Proje dosyası kolayca dönüştürür ve bir geçiş raporu üretir. Raporda, ilgilenmemiz gerekebilecek sorunlar hakkında bize haber veren birkaç giriş vardır. Bildirilen bir sorun şunlardır (bu konu boyunca hata iletilerinin bazen okunabilirlik için kısaltılmış olduğunu unutmayın, örneğin tüm yolları kaldırmak için):

```Output
ComSpyAudit\ComSpyAudit.vcproj: MSB8012: $(TargetPath) ('C:\Users\UserName\Desktop\spy\spy\ComSpyAudit\.\XP32_DEBUG\ComSpyAudit.dll') does not match the Librarian's OutputFile property value '.\XP32_DEBUG\ComSpyAudit.dll' ('C:\Users\UserName\Desktop\spy\spy\XP32_DEBUG\ComSpyAudit.dll') in project configuration 'Unicode Debug|Win32'. This may cause your project to build incorrectly. To correct this, please make sure that $(TargetPath) property value matches the value specified in %(Lib.OutputFile).
```

Projeleri yükseltmede sık karşılaşılan sorunlardan biri, proje özellikleri iletişim kutusundaki **Bağlayıcı ÇıktıDosyası** ayarının gözden geçirilmesi gerekebilir. Visual Studio 2010'dan önceki projelerde OutputFile, standart olmayan bir değere ayarlanmışsa otomatik dönüşüm sihirbazı ile sorun yaşıyor bir ayardır. Bu durumda, çıktı dosyalarının yolları standart olmayan bir klasöre, XP32_DEBUG olarak ayarlanmıştır. Bu hata hakkında daha fazla bilgi edinmek için, biz visual studio 2010 proje yükseltme, vcbuild msbuild, önemli bir değişiklik değişiklik dahil yükseltme ile ilgili bir [blog yazısı](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/) danıştı. Bu bilgilere göre, yeni bir proje oluşturduğunuzda **Çıktı** Dosyası `$(OutDir)$(TargetName)$(TargetExt)`ayarı için varsayılan değer , ancak dönüştürülmüş projeler için her şeyin doğru olduğunu doğrulamak mümkün değildir çünkü bu dönüşüm sırasında ayarlanmaz. Ancak, OutputFile için koyarak deneyelim ve çalışıp çalışmadığını görelim.  Öyle, böylece devam edebiliriz. Standart olmayan bir çıktı klasörü kullanmak için özel bir neden yoksa, standart konumu kullanmanızı öneririz. Bu durumda, taşıma ve yükseltme işlemi sırasında çıktı konumunu standart olmayan olarak bırakmayı seçtik; `$(OutDir)` **Hata Ayıklama** yapılandırmasındaki XP32_DEBUG klasörüne ve **ReleaseU** yapılandırmasına yönelik ReleaseU klasörüne gider.

### <a name="step-2-getting-it-to-build"></a>2. Adım İnşa etmesini sağlamak

Taşınan projeyi oluşturmak, bir takım hatalar ve uyarılar oluşur.

`ComSpyCtl`bu derleyici hatası nedeniyle derlemez:

```Output
atlcom.h(611): error C2664: 'HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM,BOOL,ATL::ATL_PROPMAP_ENTRY *)': cannot convert argument 3 from 'const ATL::ATL_PROPMAP_ENTRY *' to 'ATL::ATL_PROPMAP_ENTRY *'atlcom.h(611): note: Conversion loses qualifiersatlcom.h(608): note: while compiling class template member function 'HRESULT ATL::IPersistStreamInitImpl<CComSpy>::Save(LPSTREAM,BOOL)'\spy\spy\comspyctl\ccomspy.h(28): note: see reference to class template instantiation 'ATL::IPersistStreamInitImpl<CComSpy>' being compiled
```

Hata, atlcom.h'deki sınıftaki `Save` yönteme `IPersistStreamInitImpl` başvurur.

```cpp
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)
{
     T* pT = static_cast<T*>(this);
     ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));
     return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());
}
```

Sorun, derleyicinin kabul edilen eski bir sürümünün artık geçerli olmadığı bir dönüştürmedir. C++ standardına uymak için, daha önce izin verilen bazı kodlara artık izin verilmez. Bu durumda, const işaretçisi bekleyen bir işleve const olmayan bir işaretçi geçmek güvenli değildir.  Çözüm, sınıfın bildirimini `IPersistStreamInit_Save` `CComSpy` bulmak ve const değiştiriciyi üçüncü parametreye eklemektir.

```cpp
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)
```

Ve benzer bir `IPersistStreamInit_Load`değişiklik .

```cpp
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);
```

Bir sonraki hata kayıt ile ilgilidir.

```Output
error MSB3073: The command "regsvr32 /s /c "C:\Users\username\Desktop\spy\spy\ComSpyCtl\.\XP32_DEBUG\ComSpyCtl.lib"error MSB3073: echo regsvr32 exec. time > ".\XP32_DEBUG\regsvr32.trg"error MSB3073:error MSB3073: :VCEnd" exited with code 3.
```

Artık bu post-build kayıt komutuna ihtiyacımız yok. Bunun yerine, yalnızca özel yapı komutunu kaldırırız ve çıktıyı kaydetmek için **Bağlayıcı** ayarlarında belirtiriz.

### <a name="dealing-with-warnings"></a>Uyarılarla başa çıkma

Proje aşağıdaki bağlayıcı uyarısını üretir.

```Output
warning LNK4075: ignoring '/EDITANDCONTINUE' due to '/SAFESEH' specification
```

`/SAFESEH` Derleyici seçeneği hata ayıklama modunda yararlı değildir, bu `/EDITANDCONTINUE` nedenle buradaki düzeltme yalnızca `/SAFESEH` Hata **Ayıklama** yapılandırmaları için devre dışı kalmaktır. Özellik iletişim kutusunda bunu yapmak için, bu hatayı üreten proje için özellik iletişim kutusunu açarız ve **yapılandırmayı** önce **Hata** Ayıklama (aslında **Hata Ayıklama Unicode)** olarak ayarlıyoruz ve`/SAFESEH:NO`ardından Bağlayıcı **Gelişmiş** **bölümünde, Görüntü Nün Güvenli Özel Durum İşleyicileri** özelliğini **sıfırlıyoruz** ( ).

Derleyici bu amortisman `PROP_ENTRY_EX` alıto olduğunu bizi uyarır. Güvenli değil ve önerilen yerine `PROP_ENTRY_TYPE_EX`.

```cpp
BEGIN_PROPERTY_MAP(CComSpy)
     PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_PAGE(CLSID_StockFontPage)
END_PROPERTY_MAP()
```

Uygun olarak COM türleri ekleyerek, buna göre ccomspy.h kodu değiştirin.

```cpp
BEGIN_PROPERTY_MAP(CComSpy)
     PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)
     PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)
     PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)
     PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)
     PROP_PAGE(CLSID_StockFontPage)
END_PROPERTY_MAP()
```

Biz de daha sıkı derleme uygunluk kontrolleri neden olan son birkaç uyarılar, aşağı alıyoruz:

```Output
\spy\comspyctl\usersub.h(70): warning C4457: declaration of 'var' hides function parameter\spy\comspyctl\usersub.h(48): note: see declaration of 'var'\spy\comspyctl\usersub.h(94): warning C4018: '<': signed/unsigned mismatch  ComSpy.cpp\spy\comspyctl\comspy.cpp(186): warning C4457: declaration of 'bHandled' hides function parameter\spy\spy\comspyctl\comspy.cpp(177): note: see declaration of 'bHandled'
```

Uyarı C4018 bu koddan gelir:

```cpp
for (i=0;i<lCount;i++)
    CoTaskMemFree(pKeys[i]);
```

Sorun `i` olarak `UINT` beyan edilir `lCount` ve **uzun**olarak ilan edilir , dolayısıyla imzalı / imzasız uyumsuzluk. Bu tür `lCount` değiştirmek için sakıncalı `UINT`olacaktır , çünkü değerini `IMtsEventInfo::get_Count`alır , hangi türü **uzun**kullanır , ve kullanıcı kodunda değildir. Bu yüzden koda bir döküm ekliyoruz. C tarzı bir döküm böyle bir sayısal döküm için yapardı, ancak **static_cast** önerilen stildir.

```cpp
for (i=0;i<static_cast<UINT>(lCount);i++)
    CoTaskMemFree(pKeys[i]);
```

Bu uyarılar, aynı ada sahip bir parametreye sahip bir işlevde bir değişkenin bildirildiği ve bu nedenle kafa karıştırıcı koda yol açan durumlardır. Bunu yerel değişkenlerin adlarını değiştirerek düzeltdik.

### <a name="step-3-testing-and-debugging"></a>3. Adım Test etme ve hata ayıklama

Uygulamayı önce çeşitli menü ve komutları çalıştırarak ve ardından uygulamayı kapatarak test ettik. Dikkat çeken tek sorun, uygulamayı kapattıktan sonra hata ayıklama iddiasıydı. Sorun, `CWindowImpl` `CSpyCon` nesnenin bir taban sınıfı, uygulamanın ana COM bileşeni için yıkıcı ortaya çıktı. İddia hatası atlwin.h'de aşağıdaki kodda oluştu.

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

Normalde `hWnd` `WindowProc` işlevde sıfır olarak ayarlanır, ancak bu gerçekleşmedi çünkü varsayılan `WindowProc`yerine, pencereyi kapatan Windows iletisi (WM_SYSCOMMAND) için özel bir işleyici çağrılır. Özel işleyici sıfıra `hWnd` ayar değildi. MFC'nin `CWnd` `OnNcDestroy` sınıfındaki benzer koda bakıldığında, bir pencere yok edilirken çağrıldığı ve MFC'de belgelerin `CWnd::OnNcDestroy`geçersiz `NcDestroy` kılındığında, pencere tutamacını pencereden ayırmak veya başka bir deyişle sıfıra ayarlamak `hWnd` da dahil olmak üzere doğru temizleme işlemlerinin oluştuğundan emin olmak için tabanın çağrılması gerektiği önerir. Aynı iddia kodu atlwin.h'nin eski sürümünde bulunduğundan, bu assert örneğin özgün sürümünde de tetiklenmiş olabilir.

Uygulamanın işlevselliğini test etmek için, ATL proje şablonu kullanarak bir **Serviced Bileşeni** oluşturduk, ATL proje sihirbazına COM+ desteği eklemeyi seçtik. Daha önce hizmet edilen bileşenlerle çalışmadıysanız, bir tane oluşturmak ve diğer uygulamaların kullanması için sistemde veya ağda kayıtlı ve kullanılabilir hale getirmek zor değildir. COM Spy uygulaması, bir tanı sallım yardımı olarak hizmet görülen bileşenlerin faaliyetlerini izlemek için tasarlanmıştır.

Sonra bir sınıf ekledik, ATL Nesnesi'ni seçtik ve nesne adını `Dog`. Sonra dog.h ve dog.cpp, biz uygulama ekledi.

```cpp
STDMETHODIMP CDog::Wag(LONG* lDuration)
{
    // TODO: Add your implementation code here
    *lDuration = 100l;
    return S_OK;
}
```

Daha sonra, biz inşa ve kaydetti (Yönetici olarak Visual Studio çalıştırmak gerekir), ve Windows Denetim Masası'nda **Serviced Bileşeni** uygulamasını kullanarak etkinleştirdi. Bir C# Windows Forms projesi oluşturduk, bir düğmeyi araç kutusundan forma sürükledik ve bunu bir tıklama olayı işleyicisine çift tıklattık. Bileşeni anında sağlamak için aşağıdaki kodu `Dog` ekledik.

```cpp
private void button1_Click(object sender, EventArgs e)
{
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();
    dog1.Wag();
}
```

Bu sorunsuz koştu ve COM Spy kadar ve çalışan `Dog` ve bileşeni izlemek için yapılandırılan, veri çok etkinliği gösteren görünür.

## <a name="see-also"></a>Ayrıca bkz.

[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Sonraki Örnek: Spy++](../porting/porting-guide-spy-increment.md)<br/>
[Önceki Örnek: MFC Karalama](../porting/porting-guide-mfc-scribble.md)
