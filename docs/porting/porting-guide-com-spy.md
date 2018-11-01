---
title: 'Taşıma Kılavuzu: COM Spy'
ms.date: 11/04/2016
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
ms.openlocfilehash: 67dbcc815404c26535763239eddb176fcecf03f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441799"
---
# <a name="porting-guide-com-spy"></a>Taşıma Kılavuzu: COM Spy

Bu konuda, daha eski Visual C++ projelerini Visual Studio'nun en son sürüme yükseltme işlemini gösteren makaleler serisinin saniyedir. Bu konudaki örnek kod, en son Visual Studio 2005 ile derlendi.

## <a name="comspy"></a>COMSpy

COMSpy izler ve hizmet verilen bileşenleri bir makineye etkinlik günlükleri bir programdır. Hizmet verilen bileşenleri bir sistem üzerinde çalışan ve aynı ağdaki bilgisayarlar tarafından kullanılabilen COM + bileşenleri şunlardır. Windows Denetim Masası'ndaki Bileşen Hizmetleri'ni işlevi tarafından yönetildikleri.

### <a name="step-1-converting-the-project-file"></a>Adım 1. Proje dosyası dönüştürülüyor.
Proje dosyası, kolayca dönüştürür ve geçiş raporu üretir. Biz uğraşmanız gerekebilecek sorunlar hakkında bize bildirmek rapordaki bazı girişler vardır. Bildirilen bir sorun İşte (Bu konu başlığı altında yaptığımız, hata iletileri bazen örneğin tam yollarını kaldırmak, okunabilirlik için kısaltılmış olduğunu unutmayın):

```Output
ComSpyAudit\ComSpyAudit.vcproj: MSB8012: $(TargetPath) ('C:\Users\UserName\Desktop\spy\spy\ComSpyAudit\.\XP32_DEBUG\ComSpyAudit.dll') does not match the Librarian's OutputFile property value '.\XP32_DEBUG\ComSpyAudit.dll' ('C:\Users\UserName\Desktop\spy\spy\XP32_DEBUG\ComSpyAudit.dll') in project configuration 'Unicode Debug|Win32'. This may cause your project to build incorrectly. To correct this, please make sure that $(TargetPath) property value matches the value specified in %(Lib.OutputFile).
```

Projeleri yükseltme sırasında sık sık sorunlardan biri olan **bağlayıcı OutputFile** Proje Özellikleri iletişim kutusunda ayar gözden geçirilmesi gerekebilir. Standart olmayan bir değere ayarlarsanız Visual Studio 2010'dan önceki projelerde OutputFile, sorun otomatik dönüştürme Sihirbazı'nı içeren bir ayardır. Bu durumda, Çıkış dosyalarını yollarını standart olmayan bir klasör, XP32_DEBUG ayarlandı. Bu hata hakkında daha fazla bilgi için biz consulted bir [blog gönderisi](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx) vcbuild değişiklik MSBuild, önemli bir değişiklik söz konusu yükseltme olan Visual C++ 2010 proje yükseltme, ilgili. Bu bilgiler göre varsayılan değer için **çıkış dosyası** yeni bir proje oluşturduğunuzda ayardır `$(OutDir)$(TargetName)$(TargetExt)`, ancak doğrulamak, dönüştürülen projelerde mümkün olmadığından, bu dönüştürme sırasında ayarlanmamış her şeyin doğru mu? Bununla birlikte, şimdi, OutputFile için yerleştirmeyi deneyin ve çalışıp çalışmadığına bakabilirsiniz.  Biz hareket edecek şekilde bunu, yapar. Standart olmayan bir çıkış klasörü kullanılarak hiçbir belirli bir neden varsa, standart konumu kullanmanızı öneririz. Bu durumda, taşıma ve yükseltme işlemi sırasında çıkış konumu standart dışı olarak bırakmak seçtik; `$(OutDir)` XP32_DEBUG klasörüne çözümler **hata ayıklama** yapılandırma ve ReleaseU klasörünü **yayın** yapılandırma.

### <a name="step-2-getting-it-to-build"></a>Adım 2. Derleme için alma
Taşınmasını proje oluşturma, hataları ve Uyarıları birkaç oluşur.

`ComSpyCtl` Ancak bu derleyici hatası nedeniyle derleme değil:

```Output
atlcom.h(611): error C2664: 'HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM,BOOL,ATL::ATL_PROPMAP_ENTRY *)': cannot convert argument 3 from 'const ATL::ATL_PROPMAP_ENTRY *' to 'ATL::ATL_PROPMAP_ENTRY *'atlcom.h(611): note: Conversion loses qualifiersatlcom.h(608): note: while compiling class template member function 'HRESULT ATL::IPersistStreamInitImpl<CComSpy>::Save(LPSTREAM,BOOL)'\spy\spy\comspyctl\ccomspy.h(28): note: see reference to class template instantiation 'ATL::IPersistStreamInitImpl<CComSpy>' being compiled
```

Hata başvuruları `Save` metodunda `IPersistStreamInitImpl` atlcom.h sınıfta.

```cpp
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)
{
     T* pT = static_cast<T*>(this);
     ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));
     return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());
}
```

Derleyici daha eski bir sürümünü kabul dönüştürme artık geçerli olmadığını sorunudur. C++ standardı ile uyumlu için daha önce izin verilen bazı kod artık izin verilmez. Bu durumda, sabit olmayan bir işaretçi bir const işaretçisi bekleyen bir işleve geçirilecek güvenli değildir.  Çözüm bildirimi bulmaktır `IPersistStreamInit_Save` üzerinde `CComSpy` sınıfı ve üçüncü parametre const değiştirici ekleyin.

```cpp
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)
```

Ve benzer bir değişiklik `IPersistStreamInit_Load`.

```cpp
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);
```

Sonraki hata kaydı ile ilgilidir.

```Output
error MSB3073: The command "regsvr32 /s /c "C:\Users\username\Desktop\spy\spy\ComSpyCtl\.\XP32_DEBUG\ComSpyCtl.lib"error MSB3073: echo regsvr32 exec. time > ".\XP32_DEBUG\regsvr32.trg"error MSB3073:error MSB3073: :VCEnd" exited with code 3.
```

Bu derleme sonrası kayıt komutu artık gerekmez. Bunun yerine, biz yalnızca özel oluşturma komutu kaldırın ve belirttiğiniz **bağlayıcı** çıkış kaydetmek için ayarlar.

### <a name="dealing-with-warnings"></a>Uyarılarla ilgilenme
Uyarı aşağıdaki bağlayıcı projesi oluşturur.

```Output
warning LNK4075: ignoring '/EDITANDCONTINUE' due to '/SAFESEH' specification
```

`/SAFESEH` Derleyici seçeneği olduğunda hata ayıklama modunda kullanışlı değildir `/EDITANDCONTINUE` düzeltme burada devre dışı bırakmak için bu nedenle yararlıdır `/SAFESEH` için **hata ayıklama** yapılandırmalar. Özellik iletişim kutusunda bunun için Biz bu hatayı üretir projenin özellik iletişim kutusunu açın ve ilk ayarlarız **yapılandırma** için **hata ayıklama** (aslında **hata ayıklama Unicode**) ve ardından **bağlayıcı Gelişmiş** bölümünde, sıfırlama **görüntü güvenli özel durum işleyicileri var** özelliğini **Hayır** (`/SAFESEH:NO`).

Derleyici bize uyarır, `PROP_ENTRY_EX` kullanım dışı bırakılmıştır. Önerilen alternatif güvenli değil ve `PROP_ENTRY_TYPE_EX`.

```cpp
BEGIN_PROPERTY_MAP(CComSpy)
     PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_PAGE(CLSID_StockFontPage)
END_PROPERTY_MAP()
```

Biz ccomspy.h kodunda uygun şekilde, COM türleri uygun şekilde ekleme değiştirin.

```cpp
BEGIN_PROPERTY_MAP(CComSpy)
     PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)
     PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)
     PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)
     PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)
     PROP_PAGE(CLSID_StockFontPage)
END_PROPERTY_MAP()
```

Biz son tarafından daha katı derleyici uyumluluğu denetimleri de neden bazı uyarılar bir fiyatla karşılaşacağınız:

```Output
\spy\comspyctl\usersub.h(70): warning C4457: declaration of 'var' hides function parameter\spy\comspyctl\usersub.h(48): note: see declaration of 'var'\spy\comspyctl\usersub.h(94): warning C4018: '<': signed/unsigned mismatch  ComSpy.cpp\spy\comspyctl\comspy.cpp(186): warning C4457: declaration of 'bHandled' hides function parameter\spy\spy\comspyctl\comspy.cpp(177): note: see declaration of 'bHandled'
```

Uyarı C4018 bu koddan gelir:

```cpp
for (i=0;i<lCount;i++)
    CoTaskMemFree(pKeys[i]);
```

Sorun `i` olarak bildirilen `UINT` ve `lCount` olarak bildirilen **uzun**, bu nedenle imzalı/imzasız uyuşmazlığı. Türünü değiştirmek olmayacağı `lCount` için `UINT`, değerini aldığından `IMtsEventInfo::get_Count`, türü kullanır **uzun**ve kullanıcı kodunda değil. Bu nedenle bir tür dönüştürme için kod ekleyeceğiz. Bunun gibi bir sayısal dönüştürme için bir C stili tür dönüştürme yapabilirsiniz ancak **static_cast** önerilen stili.

```cpp
for (i=0;i<static_cast<UINT>(lCount);i++)
    CoTaskMemFree(pKeys[i]);
```

Bu uyarı, bir değişken için büyük olasılıkla kod kafa karıştırıcı önde gelen aynı adlı bir parametreye sahip bir işlev nerede bildirildi örnekleridir. Yerel değişkenlerin adlarını değiştirerek düzelttik.

### <a name="step-3-testing-and-debugging"></a>Adım 3. Test ve hata ayıklama
Uygulamayı ilk kez çeşitli menüler ve komutlar çalıştıran ve ardından uygulamayı kapatarak test. Belirtilen tek sorun uygulamayı kapatma sırasında bir hata ayıklama onaylama işlemi oluştu. Sorun yok Edicisi görünen `CWindowImpl`, temel bir sınıfı `CSpyCon` nesnesi, uygulamanın ana COM bileşeni. Aşağıdaki kodda atlwin.h onaylama işlemi hatası oluştu.

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

`hWnd` Normalde sıfıra ayarlanır `WindowProc` işlevi, ancak siz meydana çünkü varsayılan yerine `WindowProc`, özel bir işleyici pencereyi kapatır Windows iletisi (WM_SYSCOMMAND) olarak adlandırılır. Özel işleyici ayarlamıyor `hWnd` sıfır. MFC'nin benzer bir kod göz `CWnd` sınıfı, gösteren bir pencere ediliyorken `OnNcDestroy` belgeleri, öneren geçersiz kılarken denir ve MFC içinde olduğu `CWnd::OnNcDestroy`, temel `NcDestroy` emin olmak için çağrılmalıdır sağ temizleme işlemleri ortaya, pencere işleyicisi penceresinden ayırarak dahil olmak üzere veya diğer bir deyişle, ayarı `hWnd` sıfır. Aynı onay kodunu atlwin.h'ın eski sürümünde mevcut olduğundan bu onay örnek de, orijinal sürümünde Tetiklenmiş olabilir.

Uygulamanın işlevselliğini test etmek için oluşturduğumuz bir **hizmet bileşeni** ATL Proje şablonunu kullanarak seçtiğiniz ATL projesi Sihirbazı'nda COM + desteği eklemek. Önce hizmet verilen bileşenleri ile çalışmadıysanız oluşturun ve kayıtlı ve sistem veya ağ kullanmak diğer uygulamaları için kullanılabilir edinebileceğinizi zor değildir. COM Spy uygulama tanılama Yardımcısı olarak hizmet verilen bileşenleri etkinliğini izlemek için tasarlanmıştır.

Biz bir sınıf eklenen ATL nesnesi seçtiniz ve nesne adı olarak belirtilen `Dog`. Ardından dog.h ve dog.cpp, uygulama ekledik.

```cpp
STDMETHODIMP CDog::Wag(LONG* lDuration)
{
    // TODO: Add your implementation code here
    *lDuration = 100l;
    return S_OK;
}
```

Ardından, biz yerleşik ve (Visual Studio'yu yönetici olarak çalıştırmanız gerekir), kayıtlı ve bunu kullanarak etkin **hizmet bileşeni** Windows Denetim Masası'nda uygulama. Biz bir C# Windows Forms projesi oluşturduktan, bir düğme araç kutusundan forma sürüklediğiniz ve, bir tıklama olayı işleyicisi için eklemiştir. Örneği oluşturmak için aşağıdaki kodu ekledik `Dog` bileşeni.

```cpp
private void button1_Click(object sender, EventArgs e)
{
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();
    dog1.Wag();
}
```

Bu sorunları olmadan ve COM Spy çalışmaya çalıştı ve izlemek için yapılandırılır `Dog` bileşeni çok fazla veri görünür etkinliğini gösteren.

## <a name="see-also"></a>Ayrıca Bkz.

[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Sonraki örnek: Spy ++](../porting/porting-guide-spy-increment.md)<br/>
[Önceki örnek: MFC Scribble](../porting/porting-guide-mfc-scribble.md)