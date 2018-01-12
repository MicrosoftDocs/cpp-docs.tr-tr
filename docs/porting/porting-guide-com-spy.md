---
title: "Taşıma Kılavuzu: COM Spy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1b3473d7cd4ec23749f95bd06a1d993abc3209df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="porting-guide-com-spy"></a>Taşıma Kılavuzu: COM Spy
Bu konu, daha eski Visual C++ projeleri Visual Studio en son sürüme yükseltme işlemi gösteren bir dizi makaleleri saniyedir. Bu konudaki örnek kod, en son Visual Studio 2005 ile derlendi.  
  
## <a name="comspy"></a>COMSpy  
 COMSpy izler ve hizmet verilen bileşenleri bir makineye etkinliğini günlüğe bir programdır. Hizmet verilen bileşenleri bir sistemde çalıştırmak ve aynı ağdaki bilgisayarlar tarafından kullanılabilen COM + bileşenlerdir. Windows Denetim Masası'ndaki Bileşen Hizmetleri işlevleri tarafından yönetilen.  
  
### <a name="step-1-converting-the-project-file"></a>Adım 1. Proje dosyası dönüştürülüyor.  
 Proje dosyası kolayca dönüştürür ve geçiş raporu üretir. Bize bildirin uğraşmanız ihtiyacımız sorunlar hakkında rapor birkaç girişleri yoktur. Bildirilen sorunlardan biri İşte (Bu konu boyunca, hata iletileri bazen örneğin tam yollarını kaldırmak okunabilirlik için kısaltılmış olduğunu unutmayın):  
  
```Output  
ComSpyAudit\ComSpyAudit.vcproj: MSB8012: $(TargetPath) ('C:\Users\UserName\Desktop\spy\spy\ComSpyAudit\.\XP32_DEBUG\ComSpyAudit.dll') does not match the Librarian's OutputFile property value '.\XP32_DEBUG\ComSpyAudit.dll' ('C:\Users\UserName\Desktop\spy\spy\XP32_DEBUG\ComSpyAudit.dll') in project configuration 'Unicode Debug|Win32'. This may cause your project to build incorrectly. To correct this, please make sure that $(TargetPath) property value matches the value specified in %(Lib.OutputFile).  
```  
  
 Projeleri yükseltme sık rastlanan sorunları Proje Özellikleri iletişim kutusu bağlayıcı ÇıktıDosyası ayarında gözden geçirilmesi gerekebilir biridir. Standart olmayan bir değere ayarlarsanız Visual Studio 2010 önce projelerde ÇıktıDosyası, sorun otomatik dönüştürme Sihirbazı'nı olan bir ayardır. Bu durumda, yolları çıkış dosyaları için standart olmayan bir klasör, XP32_DEBUG ayarlandı. Bu hata hakkında daha fazla bilgi için biz consulted bir [blog gönderisi](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx) msbuild, önemli bir değişiklik vcbuild değişikliği söz konusu yükseltmenin olduğu Visual C++ 2010 proje yükseltme ilgili. Bu bilgi göre yeni bir proje oluşturduğunuzda, çıktı dosyası ayarı için varsayılan değer: $(OutDir)$(TargetName)$(TargetExt) ayarlanmış, ancak bu değil dönüştürme sırasında her şeyi olduğunu doğrulamak, dönüştürülmüş projelerde mümkün olmadığından düzeltin.  Ancak, şimdi uygulamasında ÇıktıDosyası yerleştirmeyi deneyin ve çalışıp çalışmadığını.  Biz hareket edecek şekilde bunu, yapar. Standart olmayan bir çıkış klasörü kullanmak için belirli bir sebep ise, standart konumu kullanmanızı öneririz. Bu durumda, taşıma ve yükseltme işlemi sırasında çıkış konumu standart dışı olarak bırakmak seçtik; Hata ayıklama yapılandırmasını XP32_DEBUG klasöründe ve yayın yapılandırma için ReleaseU klasör $(OutDir) çözümler.  
  
### <a name="step-2-getting-it-to-build"></a>Adım 2. Derleme için alma  
 Taşınmasını projesi oluşturma, hataları ve uyarıları sayısı oluşur.  
  
 ComSpyCtl rağmen bu derleyici hatası nedeniyle derleme değil:  
  
```Output  
atlcom.h(611): error C2664: 'HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM,BOOL,ATL::ATL_PROPMAP_ENTRY *)': cannot convert argument 3 from 'const ATL::ATL_PROPMAP_ENTRY *' to 'ATL::ATL_PROPMAP_ENTRY *'atlcom.h(611): note: Conversion loses qualifiersatlcom.h(608): note: while compiling class template member function 'HRESULT ATL::IPersistStreamInitImpl<CComSpy>::Save(LPSTREAM,BOOL)'\spy\spy\comspyctl\ccomspy.h(28): note: see reference to class template instantiation 'ATL::IPersistStreamInitImpl<CComSpy>' being compiled  
```  
  
 Hata atlcom.h IPersistStreamInitImpl sınıfında Kaydet yöntemi başvurur.  
  
```cpp  
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)  
{  
     T* pT = static_cast<T*>(this);  
     ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));  
     return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());  
}  
```  
  
 Derleyici daha eski bir sürümü kabul dönüştürme artık geçerli olmadığını sorunudur. C++ Standart uygun olması için daha önce izin verildiği biraz kod artık izin verilir. Bu durumda, bir sabit olmayan işaretçi const işaretçisi bekleyen bir işleve geçirmek güvenli değil.  IPersistStreamInit_Save bildirimi CComSpy sınıfında bulmak ve const değiştiricisi üçüncü bir parametre eklemek için çözümüdür.  
  
```cpp  
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)  
  
```  
  
 Ve IPersistStreamInit_Load benzer bir değişiklik.  
  
```cpp  
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);  
```  
  
 Sonraki hata kaydı ile ilgilidir.  
  
```Output  
error MSB3073: The command "regsvr32 /s /c "C:\Users\username\Desktop\spy\spy\ComSpyCtl\.\XP32_DEBUG\ComSpyCtl.lib"error MSB3073: echo regsvr32 exec. time > ".\XP32_DEBUG\regsvr32.trg"error MSB3073:error MSB3073: :VCEnd" exited with code 3.  
```  
  
 Bu oluşturma sonrası kayıt komutu artık gerekli değil. Bunun yerine, biz yalnızca özel derleme komutu kaldırın ve çıktı kaydetmek için bağlayıcı ayarlarını belirtin.  
  
### <a name="dealing-with-warnings"></a>Uyarılarla ele alma  
 Proje uyarı aşağıdaki bağlayıcı oluşturur.  
  
```Output  
warning LNK4075: ignoring '/EDITANDCONTINUE' due to '/SAFESEH' specification  
```  
  
 SAFESEH derleyici seçeneği yararlı SAFESEH yalnızca hata ayıklama yapılandırmaları için devre dışı bırakmak için düzeltme burada olacak şekilde /EDITANDCONTINUE yararlıdır bağlandığınızda hata ayıklama modunda değil. Bu özellik iletişim kutusunda yapmak için Biz bu hatayı üreten projesi için özellik iletişim kutusunu açın ve biz ilk (gerçekten hata ayıklama Unicode) hata ayıklamak için yapılandırmasını ayarlayın ve ardından bağlayıcı Gelişmiş bölümünde görüntü güvenli özel durum işleyicileri sahip özellik sıfırlayın Hayır (/ SAFESEH:NO).  
  
 Derleyici bize PROP_ENTRY_EX kullanım dışıdır konusunda sizi uyarır. Güvenli değilse ve önerilen alternatif PROP_ENTRY_TYPE_EX.  
  
```cpp  
BEGIN_PROPERTY_MAP(CComSpy)  
     PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)  
     PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)  
     PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)  
     PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)  
     PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 Biz ccomspy.h kodda buna uygun olarak, COM türleri uygun şekilde ekleme değiştirin.  
  
```cpp  
BEGIN_PROPERTY_MAP(CComSpy)  
     PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)  
     PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
     PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
     PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)  
     PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 Ki şu anda son tarafından daha katı derleyici uyumluluğu denetimleri de nedeniyle birkaç uyarıları alınıyor:  
  
```Output  
\spy\comspyctl\usersub.h(70): warning C4457: declaration of 'var' hides function parameter\spy\comspyctl\usersub.h(48): note: see declaration of 'var'\spy\comspyctl\usersub.h(94): warning C4018: '<': signed/unsigned mismatch  ComSpy.cpp\spy\comspyctl\comspy.cpp(186): warning C4457: declaration of 'bHandled' hides function parameter\spy\spy\comspyctl\comspy.cpp(177): note: see declaration of 'bHandled'  
```  
  
 Uyarı C4018 bu koddan gelir:  
  
```cpp  
for (i=0;i<lCount;i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 , İ UINT bildirilmiş ve lCount uzun, bu nedenle imzalı ve imzasız uyuşmazlığı bildirilmiş sorunudur. Hangi tür uzun kullanır ve kullanıcı kodu değil IMtsEventInfo::get_Count gelen değeri aldığından UINT için lCount türünü değiştirmek zor olacaktır. Böylece biz bir cast kodu ekleyin. C tarzı cast bu gibi sayısal bir atama için yaptığınız, ancak önerilen stil static_cast gelir.  
  
```cpp  
for (i=0;i<static_cast<UINT>(lCount);i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 Bu uyarılar kodu potansiyel olarak kafa karıştırıcı için önde gelen aynı ada sahip bir parametreye sahip bir işlevdeki bir değişken olduğu bildirildi örnekleridir. Biz, yerel değişkenleri adlarını değiştirerek sabit.  
  
### <a name="step-3-testing-and-debugging"></a>Adım 3. Test ve hata ayıklama  
 Uygulamayı ilk çeşitli menüleri ve komutları çalıştıran ve ardından uygulamayı kapatarak test. Uygulamasını kapatma sırasında bir hata ayıklama onaylama not ettiğiniz yalnızca sorun oluştu. Sorun CWindowImpl, uygulamanın ana COM bileşeni CSpyCon nesnenin temel sınıf yıkıcı görüldü. Aşağıdaki kodda atlwin.h onaylama hatası oluştu.  
  
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
  
 HWnd normalde WindowProc işlevinde sıfır olarak ayarlanmış, ancak varsayılan WindowProc yerine özel bir işleyici penceresi kapanır Windows iletisi (WM_SYSCOMMAND) çağrıldığı için gerçekleşen alamadık. Özel işleyici hWnd sıfır ayarı olan bulunamadı. MFC'nin CWnd sınıfı, benzer bir kod göz gösteren bir pencere yok, OnNcDestroy çağrılır ve MFC'de, belgeler, CWnd::OnNcDestroy geçersiz kılarken öneren emin olmak için temel NcDestroy çağrılmalıdır sağ temizleyin işlemler meydana, penceresinden bir pencere tanıtıcının ayırarak dahil olmak üzere veya diğer bir deyişle, hWnd sıfır olarak ayarlayarak. Aynı onay kodunu atlwin.h eski sürümde mevcut olduğundan bu assert örnek de, özgün sürümünde harekete.  
  
 Bir hizmet bileşeni oluşturduğumuz uygulamanın işlevselliğini test etmek için ATL Proje şablonunu kullanarak seçtiğiniz ATL Proje Sihirbazı'nda COM + desteği eklemek. Önce hizmet verilen bileşenleri ile çalışılan yapmadıysanız, bir tane oluşturun ve kayıtlı ve sistem ya da diğer uygulamaların kullanmak ağ üzerinde kullanılabilir edinebileceğinizi zor değildir. COM Spy uygulama tanılama yardımcı olarak hizmet verilen bileşenleri etkinliğini izlemek için tasarlanmıştır.  
  
 Daha sonra bir sınıf eklenen, ATL nesnesi seçin ve köpek belirtilen nesne adı. Ardından dog.h ve dog.cpp, uygulama eklediğimiz.  
  
```cpp  
STDMETHODIMP CDog::Wag(LONG* lDuration)  
{  
    // TODO: Add your implementation code here  
    *lDuration = 100l;  
    return S_OK;  
}  
```  
  
 Ardından, biz yerleşik ve (Visual Studio'yu yönetici olarak çalıştırmanız gerekir), kayıtlı ve Windows Denetim Masası'ndaki bileşen hizmet uygulaması kullanarak etkinleştirildi. Biz C# Windows Forms projesi oluştururken, bir düğme forma Araç Kutusu'ndan sürüklenen ve click olay işleyicisi için çift. Köpek bileşen örneği için aşağıdaki kodu eklediğimiz.  
  
```cpp  
private void button1_Click(object sender, EventArgs e)  
{  
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();  
    dog1.Wag();  
}  
```  
  
 Bu sorunsuz ve COM Spy ayarlama ve çalıştırma çalıştıran ve köpek bileşeni çok fazla veri görünür etkinliğini gösteren izlemek için yapılandırılmış.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşıma ve yükseltme: örnekler ve örnek olay incelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [Sonraki örnek: Spy ++](../porting/porting-guide-spy-increment.md)   
 [Önceki örnek: MFC karalama](../porting/porting-guide-mfc-scribble.md)