---
title: Varolan Bir ActiveX Denetimini Güncelleştirme
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX controls [MFC], Internet
- LPK files for Internet controls
- safe for scripting and initialization (controls)
- OLE controls [MFC], upgrading to ActiveX
- CAB files, for ActiveX controls
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], packaging code for download
- upgrading ActiveX controls
- licensing ActiveX controls
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
ms.openlocfilehash: dfee42369b698956f4f91ab61a1f37e0ef06d9f1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754510"
---
# <a name="upgrading-an-existing-activex-control"></a>Varolan Bir ActiveX Denetimini Güncelleştirme

Varolan ActiveX denetimleri (eski adıyla OLE denetimleri) Internet'te değişiklik yapılmadan kullanılabilir. Ancak, performanslarını artırmak için denetimleri değiştirmek isteyebilirsiniz.

> [!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

Denetiminizi bir Web sayfasında kullanırken, başka hususlar da vardır. .ocx dosyası ve tüm destekleyici dosyalar hedef makinede olmalı veya Internet üzerinden indirilmelidir. Bu kod boyutu ve indirme süresi önemli bir husus yapar. İndirmeler imzalı bir .cab dosyasında paketlenebilir. Denetiminizi komut dosyası için güvenli ve başlatma için güvenli olarak işaretleyebilirsiniz.

Bu makalede aşağıdaki konular tartışılmaktadır:

- [İndirme için Ambalaj Kodu](#_core_packaging_code_for_downloading)

- [Komut Dosyası Ve Başlatma için Denetim Güvenli İşaretleme](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [Lisans Sorunları](#_core_licensing_issues)

- [İmza Kodu](#_core_signing_code)

- [Paletin Yönetimi](#_core_managing_the_palette)

- [Internet Explorer Tarayıcı Güvenlik Düzeyleri ve Kontrol Davranışı](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

[ActiveX Denetimleri: Optimizasyon'da](../mfc/mfc-activex-controls-optimization.md)açıklandığı gibi optimizasyonlar da ekleyebilirsiniz. Monikers özellikleri ve büyük BLOBs asynchronously indirmek için kullanılabilir, [Internet üzerinde ActiveX Denetimleri](../mfc/activex-controls-on-the-internet.md)açıklandığı gibi.

## <a name="packaging-code-for-downloading"></a><a name="_core_packaging_code_for_downloading"></a>İndirme için Ambalaj Kodu

Bu konuda daha fazla bilgi için [Packaging ActiveX Controls](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29)'e bakın.

### <a name="the-codebase-tag"></a>CODEBASE Etiketi

ActiveX denetimleri etiketi kullanarak `<OBJECT>` Web sayfalarına gömülür. `<OBJECT>` Etiketin `CODEBASE` parametresi, denetimi karşıdan yükleyecek yeri belirtir. `CODEBASE`başarılı bir şekilde farklı dosya türleri bir dizi işaret edebilir.

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>OCX Dosyasıyla CODEBASE Etiketini Kullanma

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

Bu çözüm yalnızca denetimin .ocx dosyasını karşıdan yükler ve istemci makinesine zaten yüklenmiş olan destekleyici DL'lerin olmasını gerektirir. Bu, Visual C++ ile oluşturulmuş Internet Explorer ve MFC ActiveX denetimleri için çalışır, çünkü Internet Explorer, Visual C++ denetimleri için destekleyici DL'lerle birlikte çalışır. ActiveX denetimine sahip başka bir Internet tarayıcısı bu denetimi görüntülemek için kullanılırsa, bu çözüm çalışmaz.

### <a name="using-the-codebase-tag-with-an-inf-file"></a>CODEBASE Etiketini INF Dosyasıyla Kullanma

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

Bir .inf dosyası bir .ocx ve destekleyici dosyalarının yüklenmesini denetler. Bir .inf dosyasını imzalamak mümkün olmadığından bu yöntem önerilmez (kod imzalama işaretçileri için [İmzalama Kodu'na](#_core_signing_code) bakın).

### <a name="using-the-codebase-tag-with-a-cab-file"></a>CAB Dosyasıyla CODEBASE Etiketini Kullanma

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

Dolap dosyaları, MFC kullanan ActiveX denetimlerini paketlemenin önerilen yoludur. Bir mfc ActiveX denetimini bir dolap dosyasında paketlemek, ActiveX denetiminin ve bağımlı DLL'lerin (MFC DL'ler gibi) yüklenmesini denetlemek için bir .inf dosyasının eklenmesine olanak tanır. CAB dosyası kullanmak, kodu daha hızlı indirmek için otomatik olarak sıkıştırır. Bileşen indirmek için bir .cab dosyası kullanıyorsanız, .cab dosyasının tamamını imzalamak her bir bileşenden daha hızlıdır.

### <a name="creating-cab-files"></a>CAB Dosyaları Oluşturma

Araçlar dolap dosyaları oluşturmak için artık [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)parçasıdır.

Tarafından işaret edilen `CODEBASE` dolap dosyası, ActiveX denetiminiz için .ocx dosyasını ve yüklemesini denetlemek için bir .inf dosyasını içermelidir. Denetim dosyanızın adını ve .inf dosyasını belirterek kabine dosyasını oluşturursunuz. Bu kabine dosyasında sistemde zaten var olabilecek bağımlı DL'leri eklemeyin. Örneğin, MFC DL'ler ayrı bir dolap dosyasında paketlenir ve .inf dosyası nın denetlenen tarafından yönlendirilir.

CAB dosyası oluşturma hakkında ayrıntılı bilgi için cab [dosyası oluşturma](/windows/win32/devnotes/cabinet-api-functions)bilgisine bakın.

### <a name="the-inf-file"></a>INF Dosyası

Aşağıdaki örnek, spindial.inf, destekleyen dosyaları ve MFC Spindial denetimi için gerekli sürüm bilgilerini listeler. MFC DLS'lerin konumunun bir Microsoft Web sitesi olduğuna dikkat edin. mfc42.cab Microsoft tarafından sağlanır ve imzalanır.

```
Contents of spindial.inf:
[mfc42installer]
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab
[Olepro32.dll] - FileVersion=5,
    0,
    4261,
    0
[Mfc42.dll] - FileVersion=6,
    0,
    8168,
    0
[Msvcrt.dll] - FileVersion=6,
    0,
    8168,
    0
```

### <a name="the-object-tag"></a>\<NESNE> Etiketi

Aşağıdaki örnek, MFC `<OBJECT>` Spindial örnek denetimini paketlemek için etiketi kullanarak gösteriş göstermektedir.

```
<OBJECT ID="Spindial1" WIDTH=100 HEIGHT=51
    CLASSID="CLSID:06889605-B8D0-101A-91F1-00608CEAD5B3"
    CODEBASE="http://example.microsoft.com/spindial.cab#Version=1,0,0,001">
<PARAM NAME="_Version" VALUE="65536">
<PARAM NAME="_ExtentX" VALUE="2646">
<PARAM NAME="_ExtentY" VALUE="1323">
<PARAM NAME="_StockProps" VALUE="0">
<PARAM NAME="NeedlePosition" VALUE="2">
</OBJECT>
```

Bu durumda, spindial.cab iki dosya, spindial.ocx ve spindial.inf içerecektir. Aşağıdaki komut kabine dosyasını oluşturur:

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

Parametre, `-s 6144` kod imzalama için dolapta yer ayırır.

### <a name="the-version-tag"></a>Sürüm Etiketi

Burada, CAB `#Version` dosyasıyla belirtilen bilgilerin etiketin *CLASSID* parametresi tarafından `<OBJECT>` belirtilen denetime uygulandığını unutmayın.

Belirtilen sürüme bağlı olarak, denetiminizin karşıdan yüklerini indirmeye zorlanabilirsiniz. `OBJECT` *CODEBASE* parametresi de dahil olmak üzere etiketin tam özellikleri için W3C referansına bakın.

## <a name="marking-a-control-safe-for-scripting-and-initializing"></a><a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a>Komut Dosyası Ve Başlatma için Denetim Güvenli İşaretleme

Web sayfalarında kullanılan ActiveX denetimleri komut dosyası için güvenli ve aslında güvenliyse başlatma için güvenli olarak işaretlenmelidir. Güvenli bir denetim disk IO gerçekleştirmez veya doğrudan bir makinenin belleği veya kayıtlarına erişmez.

Denetimler komut dosyası için güvenli ve kayıt defteri üzerinden başlatma için güvenli olarak işaretlenebilir. Denetimi `DllRegisterServer` komut dosyası ve kayıt defterinde kalıcılık için güvenli olarak işaretlemek için aşağıdakilere benzer girişler eklemek için değiştirin. Alternatif bir yöntem `IObjectSafety`uygulamaktır.

Komut dosyası ve kalıcılık için güvenli işaretlemek için denetiminiz için GUID'leri (Global Olarak Benzersiz Tanımlayıcılar) tanımlarsınız. Güvenli bir şekilde komut dosyası yla yazılabilir denetimler, aşağıdakilere benzer bir kayıt defteri girişi içerir:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

Kalıcı verilerden güvenli bir şekilde başharfe atılabilir denetimler, benzer bir kayıt defteri girişiyle kalıcılık için güvenli olarak işaretlenir:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

Anahtarlarınızı aşağıdaki sınıf kimliğiyle ilişkilendirmek için aşağıdakilere benzer `{06889605-B8D0-101A-91F1-00608CEAD5B3}`girişler ekleyin (denetiminizin sınıf kimliğinin yerine) ekleyin:

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

## <a name="licensing-issues"></a><a name="_core_licensing_issues"></a>Lisans Sorunları

Bir Web sayfasında lisanslı bir denetim kullanmak istiyorsanız, lisans sözleşmesinin Internet'te kullanımına izin verdiğini doğrulamanız ve bunun için bir lisans paketi dosyası (LPK) oluşturmanız gerekir.

Internet Explorer çalıştıran bilgisayar denetimi kullanmak için lisanslı değilse, lisanslı ActiveX denetimi HTML sayfasında düzgün yüklenmez. Örneğin, Visual C++ kullanılarak lisanslı bir denetim oluşturulmuşsa, denetimi kullanan HTML sayfası denetimin oluşturulduğu bilgisayara düzgün yüklenir, ancak lisans bilgileri dahil edilmedikçe farklı bir bilgisayara yüklenmez.

Internet Explorer'da lisanslı activex denetimini kullanmak için, denetim lisansının izin verdiğini doğrulamak için satıcının lisans sözleşmesini denetlemeniz gerekir:

- Yeniden Dağıtım

- Internet'te denetimin kullanımı

- Codebase parametresinin kullanımı

Lisanssız bir makinedeki HTML sayfasında lisanslı bir denetim kullanmak için bir lisans paketi dosyası (LPK) oluşturmanız gerekir. LPK dosyası, HTML sayfasında lisanslı denetimler için çalışma zamanı lisansları içerir. Bu dosya LPK_TOOL üzerinden oluşturulur. ActiveX SDK ile birlikte gelen EXE.

#### <a name="to-create-an-lpk-file"></a>LPK dosyası oluşturmak için

1. LPK_TOOL koş. EXE denetimi kullanmak için lisanslı bir bilgisayarda.

1. Lisans **Paketi Yazma Aracı** iletişim kutusunda, **Kullanılabilir Denetimler** liste kutusunda, HTML sayfasında kullanılacak her lisanslı ActiveX denetimini seçin ve **Ekle'yi**tıklatın.

1. **Çıkış & Kaydet'i** tıklatın ve LPK dosyası için bir ad yazın. Bu, LPK dosyasını oluşturur ve uygulamayı kapatır.

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>Html sayfasına lisanslı denetim gömmek için

1. HTML sayfanızı edin. HTML sayfasında, diğer \< \<OBJECT> etiketlerinden önce Lisans Yöneticisi nesnesi için object> etiketi ekleyin. Lisans Yöneticisi, Internet Explorer yüklü bir ActiveX denetimidir. Sınıf kimliği aşağıda gösterilmiştir. Lisans Yöneticisi nesnesinin LPKPath özelliğini LPK dosyasının yol ve adına ayarlayın. HTML sayfası başına yalnızca bir LPK dosyanız olabilir.

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. Lisans Yöneticisi \<etiketinden sonra lisanslı denetiminiz için OBJECT> etiketini ekleyin.

   Örneğin, Microsoft Maskeli Edit denetimini görüntüleyen bir HTML sayfası aşağıda gösterilmiştir. Birinci sınıf kimlik Lisans Yöneticisi denetimi için, ikinci sınıf kimlik maskeli edit denetimi içindir. Etiketleri daha önce oluşturduğunuz .lpk dosyasının göreli yoluna işaret etmek için değiştirin ve denetiminiz için sınıf kimliğini içeren bir nesne etiketi ekleyin.

1. NCompass \<ActiveX eklentisini kullanıyorsanız, LPK dosyanız için EMBED> özniteliğini ekleyin.

   Denetiminiz diğer Etkin özellikli tarayıcılarda görüntülenebiliyorsa (örneğin, NCompass ActiveX eklentisini kullanan \<Netscape), embed> sözdizimini aşağıda gösterildiği gibi eklemeniz gerekir.

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

Denetim lisanslama hakkında daha fazla bilgi için [ActiveX Denetimleri: ActiveX Denetimi'ni lisanslama.](../mfc/mfc-activex-controls-licensing-an-activex-control.md)

## <a name="signing-code"></a><a name="_core_signing_code"></a>İmza Kodu

Kod imzalama, kodun kaynağını belirlemek ve kod imzalandığı tarihten bu yana değişmediğini garanti etmek için tasarlanmıştır. Tarayıcı güvenlik ayarlarına bağlı olarak, kod indirilmeden önce kullanıcılar uyarılabilir. Kullanıcılar belirli sertifika sahiplerine veya şirketlere güvenmeyi seçebilir, bu durumda güvenilenler tarafından imzalanmış kod uyarı yapılmadan indirilir. Kod, kurcalanmayı önlemek için dijital olarak imzalanır.

Denetiminizin güven uyarı iletileri görüntülemeden otomatik olarak indirilebilmesini sağlamak için son kodunuzun imzalandığından emin olun. Kodu niçin imzalayacağınız hakkında ayrıntılı bilgi için ActiveX SDK'daki Authenticode ile ilgili belgeleri kontrol edin ve [CAB Dosyasını İmzalama](/windows/win32/devnotes/cabinet-api-functions)bölümüne bakın.

Güven ve tarayıcı güvenlik düzeyi ayarlarına bağlı olarak, imzalayan kişi veya şirketi tanımlamak için bir sertifika görüntülenebilir. Güvenlik düzeyi yoksa veya imzalı denetimin sertifika sahibine güvenilirse, sertifika görüntülenmez. Tarayıcı güvenlik ayarının denetiminizin indirilip indirilmediğini ve sertifikanın görüntülenip görüntülenmediğini nasıl belirleyeceği hakkında ayrıntılar için [Internet Explorer Tarayıcı Güvenlik Düzeyleri ve Denetim Davranışı'na](#_core_internet_explorer_browser_safety_levels_and_control_behavior) bakın.

Dijital imzalama garanti kodu imzalandıktan sonra değişmedi. Kodun bir karma alınır ve sertifikaya gömülür. Bu karma daha sonra kod indirildikten sonra ancak çalıştırmadan önce alınan kodun bir karma ile karşılaştırılır. Verisign gibi şirketler, kodu imzalamak için gereken özel ve ortak anahtarları sağlayabilir. ActiveX SDK, test sertifikaları oluşturmak için bir yardımcı program olan MakeCert ile birlikte gelir.

## <a name="managing-the-palette"></a><a name="_core_managing_the_palette"></a>Paletin Yönetimi

Kapsayıcılar paletbelirlemek ve bir ortam özelliği olarak kullanılabilir hale, **DISPID_AMBIENT_PALETTE.** Kapsayıcı (örneğin, Internet Explorer), bir sayfadaki tüm ActiveX denetimleri tarafından kendi paletlerini belirlemek için kullanılan bir palet seçer. Bu, ekranın titremesini önler ve tutarlı bir görünüm sunar.

Bir denetim, `OnAmbientPropertyChange` paletteki değişikliklerin bildirimini işlemek için geçersiz kılınabilir.

Bir denetim palet `OnGetColorSet` çizmek için bir renk kümesi döndürmek için geçersiz kılınabilir. Kapsayıcılar, denetimin palet farkında olup olmadığını belirlemek için iade değerini kullanır.

OCX 96 yönergeleri altında, bir denetim her zaman arka planda paletini gerçekleştirmek gerekir.

Ortam paleti özelliğini kullanmayan eski kapsayıcılar WM_QUERYNEWPALETTE ve WM_PALETTECHANGED iletileri gönderir. Denetim geçersiz `OnQueryNewPalette` kılınabilir `OnPaletteChanged` ve bu iletileri işleyebilir.

## <a name="internet-explorer-browser-safety-levels-and-control-behavior"></a><a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a>Internet Explorer Tarayıcı Güvenlik Düzeyleri ve Kontrol Davranışı

Tarayıcıda güvenlik düzeyi için kullanıcı tarafından yapılandırılabilen seçenekler vardır. Web sayfaları kullanıcının bilgisayarına zarar verebilecek etkin içerik içerebildiği için, tarayıcılar kullanıcının güvenlik düzeyi için seçenekler seçmesine olanak tanır. Bir tarayıcının güvenlik düzeylerini uygulama şekline bağlı olarak, bir denetim hiç indirilmeyebilir veya kullanıcının denetimi karşıdan yükleyip indirmeyeceğini çalışma zamanında seçmesine izin verecek bir sertifika veya uyarı iletisi görüntüler. ActiveX denetimlerinin Internet Explorer'daki yüksek, orta ve düşük güvenlik düzeyleri altında davranışı aşağıda listelenmiştir.

### <a name="high-safety-mode"></a>Yüksek Güvenlik Modu

- İmzasız denetimler karşıdan yüklenmez.

- İmzalanan denetimler, güvenilmemişse bir sertifika görüntüler (kullanıcı bundan böyle bu sertifika sahibinden her zaman koda güvenebileceğibir seçenek seçebilir).

- Yalnızca güvenli olarak işaretlenmiş denetimlerde kalıcı veriler ve/veya komut dosyası olabilir.

### <a name="medium-safety-mode"></a>Orta Güvenlik Modu

- İmzalanmamış denetimler indirmeden önce bir uyarı görüntüler.

- İmzalı denetimler, güvenilmemişse bir sertifika görüntüler.

- Güvenli olarak işaretlenmemiş denetimler bir uyarı görüntüler.

### <a name="low-safety-mode"></a>Düşük Güvenlik Modu

- Denetimler uyarı yapılmadan karşıdan yüklenir.

- Komut dosyası ve kalıcılık uyarı olmadan oluşur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC İnternet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC ActiveX Denetimleri: ActiveX Denetimini Lisanslama](../mfc/mfc-activex-controls-licensing-an-activex-control.md)
