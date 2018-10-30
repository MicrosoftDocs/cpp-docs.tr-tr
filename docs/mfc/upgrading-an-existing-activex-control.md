---
title: Varolan bir ActiveX denetimini güncelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48fee88dc991ff58bfb9178e370134ad3cdb11d8
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204632"
---
# <a name="upgrading-an-existing-activex-control"></a>Varolan Bir ActiveX Denetimini Güncelleştirme

Varolan bir ActiveX denetimleri (eski adı OLE denetimleri) yapmadan Internet üzerinde kullanılabilir. Ancak, performansı artırmak için denetimleri değiştirmek isteyebilirsiniz.

> [!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

Denetiminizi Web sayfasında kullanırken dikkat edilecek diğer noktalar vardır. .Ocx dosya ve tüm destekleyici dosyaları hedef makinede olmalıdır ya da Internet üzerinden indirilebilir. Bu kod boyutu ve önemli bir husus zaman indirme kolaylaştırır. İndirmeler imzalanmış .cab dosyasında paketlenebilir. Denetim kodlama için güvenli olarak ve başlatma için güvenli olarak işaretleyebilirsiniz.

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [İndirme için kodu paketleme](#_core_packaging_code_for_downloading)

- [Denetim güvenli bir komut dosyası oluşturma ve başlatma için işaretleme](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [Lisanslama sorunları](#_core_licensing_issues)

- [Kod imzalama](#_core_signing_code)

- [Palet yönetme](#_core_managing_the_palette)

- [Internet Explorer tarayıcı güvenlik düzeylerini ve denetimi davranışı](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

En iyi duruma getirme, açıklandığı ekleyebilirsiniz [ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md). Adlar, Özellikler'i indirmek için kullanılabilir ve büyük Blobları açıklandığı gibi zaman uyumsuz [Internet'te ActiveX denetimleri](../mfc/activex-controls-on-the-internet.md).

##  <a name="_core_packaging_code_for_downloading"></a> İndirme için kodu paketleme

Bu konu hakkında daha fazla bilgi için bkz. [paketleme ActiveX denetimlerini](https://docs.microsoft.com//previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29).

### <a name="the-codebase-tag"></a>Kod TEMELİ etiketi

ActiveX denetimlerini kullanan Web sayfaları katıştırılmış `<OBJECT>` etiketi. `CODEBASE` Parametresinin `<OBJECT>` etiket, denetimin indirileceği konumu belirtir. `CODEBASE` farklı dosya türleri bir numaradan başarıyla işaret edebilir.

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>Bir OCX dosyasıyla CODEBASE etiketini kullanarak

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

Bu çözüm yalnızca denetimin .ocx dosya indirir ve destekleyici DLL'lerin istemci makinede zaten yüklü olmasını gerektirir. Internet Explorer'ın Visual C++ denetimler için destek DLL'ler ile birlikte gelen çünkü bu Visual C++ ile oluşturulan, Internet Explorer ve MFC ActiveX denetimleri için çalışır. ActiveX denetimi özelliğine sahip olan başka bir Internet tarayıcısı bu denetimi görüntülemek için kullanılır, bu çözüm işe yaramaz.

### <a name="using-the-codebase-tag-with-an-inf-file"></a>Bir INF dosyası ile CODEBASE etiketini kullanarak

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

.İnf dosyası bir .ocx ve Tamamlayıcı dosyaları yüklenmesini kontrol edecek. .İnf dosyası açmanız mümkün olmadığı için bu yöntem önerilmez (bkz [kod imzalama](#_core_signing_code) kod imzalama işaretçiler için).

### <a name="using-the-codebase-tag-with-a-cab-file"></a>CODEBASE etiket bir CAB dosyası kullanma

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

Dolap dosyası, MFC kullan paket ActiveX denetimleri için önerilen yoldur. MFC ActiveX denetimi bir dolap dosyasında paketleme ActiveX denetimini ve bağımlı DLL'lerin (örneğin, MFC DLL) denetim yüklemesine dahil edilecek bir .inf dosyasının sağlar. CAB dosyası otomatik olarak kullanarak daha hızlı indirme için kodu sıkıştırır. Bileşen yüklemesi için bir .cab dosyası kullanıyorsanız, her ayrı ayrı bileşen tüm .cab dosyasından oturum daha hızlıdır.

### <a name="creating-cab-files"></a>CAB dosyaları oluşturma

Dolap dosyası oluşturmak için Araçlar artık parçası olan [Windows 10 SDK'sı](https://dev.windows.com/downloads/windows-10-sdk).

Dolap dosyası tarafından işaret edilen `CODEBASE` .ocx dosya, ActiveX denetimi ve yükleme denetlemek için .inf dosyası içermelidir. Denetimi dosyanızın adını belirterek dolap dosyası ve bir .inf dosyası oluşturun. Dolap dosyası bu sistemde mevcut olmayabilir bağımlı dll içermez. Örneğin, MFC DLL'leri ayrı bir dolap dosyasında paketlenir ve denetleme .inf dosyası tarafından başvurulan.

CAB dosyasının nasıl oluşturulacağı hakkında daha fazla bilgi için bkz: [CAB dosyası oluşturma](/windows/desktop/devnotes/cabinet-api-functions).

### <a name="the-inf-file"></a>INF dosyası

Aşağıdaki örnek, spindial.inf listeleri destekleyici dosyaları ve sürüm bilgileri için MFC Spindial denetim. Konum MFC DLL'leri için Microsoft Web sitesine olduğuna dikkat edin. Mfc42.cab sağlanan ve Microsoft tarafından imzalanmış.

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

### <a name="the-object-tag"></a>\<Nesne > etiketi

Kullanarak aşağıdaki örnekte gösterildiği `<OBJECT>` paketini MFC Spindial örnek denetim için etiket.

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

Bu durumda, iki dosya ve spindial.ocx spindial.inf spindial.cab içerir. Aşağıdaki komut, dolap dosyası oluşturacaksınız:

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

`-s 6144` Parametre kod imzalama için dolap alanı ayırır.

### <a name="the-version-tag"></a>Sürüm etiketi

Burada dikkat `#Version` bir CAB dosyası ile belirtilen bilgileri tarafından belirtilen denetim uygulandığı *ClassID* parametresinin `<OBJECT>` etiketi.

Belirtilen sürüme bağlı olarak, yükleme denetiminizin zorlayabilirsiniz. İçin tam belirtimlerini `OBJECT` etiketi de dahil olmak üzere *CODEBASE* parametresi, bkz: W3C başvurusu.

##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> Denetim güvenli bir komut dosyası oluşturma ve başlatma için işaretleme

Web sayfalarında kullanılan ActiveX denetimleri, komut dosyası için güvenli ve hatta güvenli olmaları durumunda başlatma için güvenli olarak işaretlenmelidir. Güvenli denetim, değil disk GÇ gerçekleştirmek veya bellek ya da bir makinenin kayıtları doğrudan erişebilirsiniz.

Denetimler, komut dosyası için güvenli ve kayıt defterinden başlatma için güvenli olarak işaretlenebilir. Değiştirme `DllRegisterServer` denetimini betikleri ve kayıt defteri Kalıcılık için güvenli olarak işaretlemek için aşağıdakine benzer bir giriş eklemek için. Alternatif bir yöntem uygulamaktır `IObjectSafety`.

Kalıcılığı ve betik oluşturma için güvenli olarak işaretlemek denetiminiz için GUID (genel benzersiz tanımlayıcı) tanımlayacaksınız. Güvenli bir şekilde yazılabilir denetimleri aşağıdakine benzer bir kayıt defteri girişi içerir:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

Kalıcı verileri güvenli bir şekilde başlatılabilir denetimleri kalıcılığı ile benzer bir kayıt defteri girdisi için güvenli olarak işaretlenir:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

Aşağıdakine benzer girişler ekleyin (sınıf kimliği yerine denetiminizin değiştirerek `{06889605-B8D0-101A-91F1-00608CEAD5B3}`) anahtarlarınızı aşağıdaki sınıf kimliği ile ilişkilendirmek için:

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

##  <a name="_core_licensing_issues"></a> Lisanslama sorunları

Bir Web sayfasındaki lisanslı bir denetim kullanmak istiyorsanız, lisans sözleşmesini Internet'te kullanımına izin verir ve bir lisans paket dosyası (LPK) oluşturulduğu doğrulamanız gerekir.

Internet Explorer'ı çalıştıran bilgisayarın denetimini kullanmak için lisanslı değilse lisanslı bir ActiveX denetimi bir HTML sayfasında doğru yüklemez. Örneğin, lisanslı bir denetim Visual C++ kullanılarak oluşturulduysa, denetimi kullanarak HTML sayfası düzgün burada denetim oluşturuldu, ancak lisans bilgilerini dahil olmadığı sürece farklı bir bilgisayarda yüklemez bilgisayarda yükleyin.

Internet Explorer'da lisanslı bir ActiveX denetimi kullanmak için lisans denetimi için izin verdiğini doğrulamak için satıcının lisans sözleşmesi işaretlemeniz gerekir:

- Yeniden Dağıtım

- Internet üzerindeki denetiminin kullanımı

- Kod temeli parametresinin kullanımı

Bir HTML sayfasında nonlicensed bir makinede lisanslı bir denetim kullanmak için bir lisans paket dosyası (LPK) oluşturmanız gerekir. Çalışma zamanı lisansları HTML sayfasındaki lisanslı denetimler için LPK dosya içerir. Bu dosya LPK_TOOL oluşturulur. ActiveX SDK'sı ile sunulan EXE. Daha fazla bilgi için MSDN Web sitesinde bkz [ http://msdn.microsoft.com ](http://msdn.microsoft.com).

#### <a name="to-create-an-lpk-file"></a>Bir LPK dosyası oluşturmak için

1. LPK_TOOL çalıştırın. EXE denetimi kullanmak için lisanslı bir bilgisayarda.

1. İçinde **lisans paketi yazma aracı** iletişim kutusundaki **kullanılabilir denetimleri** liste kutusu seçme her lisanslı HTML sayfasında kullanılacak ve ActiveX denetimi **Ekle**.

1. Tıklayın **Kaydet ve Çık** LPK dosyası için bir ad yazın. LPK dosyası oluşturun ve uygulamayı kapatın.

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>Bir HTML sayfasında lisanslı bir denetim eklemek için

1. HTML sayfanızı düzenleyin. HTML sayfasına ekleme bir \<Nesne > etiketi önce diğer Lisans Yöneticisi nesnesinin \<Nesne > etiketleri. Internet Explorer ile yüklü bir ActiveX denetimi lisans yöneticisidir. Sınıfı Kimliğine aşağıda gösterilmiştir. LPK dosyasının adını ve yolunu için License Manager LPKPath özelliğini ayarlayın. HTML sayfası başına yalnızca bir LPK dosyası olabilir.

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. INSERT \<Nesne > etiketi Lisans Yöneticisi etiketinden sonra lisanslı denetlemek için.

   Örneğin, Microsoft maskeli düzen denetimi görüntüleyen bir HTML sayfası aşağıda gösterilmektedir. Kimliği için License Manager denetimidir ilk sınıf saniye sınıfının maskeli düzen denetimi için kimliğidir. Etiketler, daha önce oluşturduğunuz .lpk dosyasının göreli yoluna işaret edecek şekilde değiştirin ve denetlemek için sınıf kimliği de dahil olmak üzere bir nesne etiketi ekleyin.

1. INSERT \<EMBED > Eklenti NCompass ActiveX kullanıyorsanız LPK dosyanız için özniteliği.

   Denetiminiz diğer görüntülenebilir etkin tarayıcılar etkin — Örneğin, Netscape eklentisi NCompass ActiveX kullanarak — eklemelisiniz \<ekleme > aşağıda gösterildiği gibi bir söz dizimi.

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

Denetim lisanslama hakkında daha fazla bilgi için bkz. [ActiveX denetimleri: ActiveX denetimini lisanslama](../mfc/mfc-activex-controls-licensing-an-activex-control.md).

##  <a name="_core_signing_code"></a> Kod imzalama

Kod, beri değişmediğini güvence altına almak için imzalanmış ve kod imzalama kod kaynağı tanımlamak için tasarlanmıştır. Tarayıcı Güvenliği ayarlara bağlı olarak, kod indirilmeden önce kullanıcıların uyarılmak. Kullanıcılar belirli sertifika sahipleri veya şirket içinde uyarı vermeden indirilecek büyük/küçük kod tarafından imzalanmış güvenilir güvenmeyi tercih edebilirsiniz. Kod üzerinde oynanmasını önlemek için dijital olarak imzalanır.

Kodunuzu son oturum açmış denetiminiz güven uyarı iletileri görüntülemeden otomatik olarak indirilebilir emin olun. Kod imzalama hakkında ayrıntılı bilgi Authenticode ActiveX SDK belgelerine bakın ve bkz [CAB dosyası imzalama](/windows/desktop/devnotes/cabinet-api-functions).

Güven ve tarayıcı güvenilirlik düzeyi ayarlara bağlı olarak, bir sertifika imzalama kişinin veya şirketin tanımlamak için görüntülenebilir. Güvenlik düzeyi none ise veya imzalı denetimin sertifika sahibinin güvenilen ise, bir sertifika görüntülenmez. Bkz [Internet Explorer tarayıcı güvenlik düzeylerini ve denetimi davranışı](#_core_internet_explorer_browser_safety_levels_and_control_behavior) ayrıntılı denetim olup indirilir ve görüntülenen bir sertifika tarayıcı güvenlik ayarı nasıl belirler.

Dijital imza garanti kod imzalanmış bu yana değişmemiştir. Bir karma kod geçen ve katıştırılmış sertifikayı. Bu karma, daha sonra bir karma kod İndirildikten sonra ancak çalıştırılmadan önce geçen kod ile karşılaştırılır. Verisign gibi şirketler kodunu imzalamak amacıyla gerekli özel ve genel anahtarlar sağlayabilirsiniz. ActiveX SDK'sı, MakeCert, test sertifikalarınızı oluşturmak için bir yardımcı programı ile birlikte gelir.

##  <a name="_core_managing_the_palette"></a> Palet yönetme

Kapsayıcılar paletini belirlemek ve bir ortam özelliği olarak kullanılabilir hale getirmek **DISPID_AMBIENT_PALETTE**. Bir kapsayıcı (örneğin, Internet Explorer) tarafından bir sayfadaki tüm ActiveX denetimleri kendi paletini belirlemek için kullanılan bir palet seçer. Bu görüntü titremeyi engeller ve tutarlı bir görünüm sunar.

Bir denetimi geçersiz kılabilirsiniz `OnAmbientPropertyChange` paleti değişiklikleri bildirimini işlemek için.

Bir denetimi geçersiz kılabilirsiniz `OnGetColorSet` bir renk paleti çizmek için kümesini döndürmek için. Kapsayıcılar, dönüş değeri bir denetim palet uyumlu olup olmadığını belirlemek için kullanın.

Bir denetim, OCX 96 yönergeleri altında her zaman bu arka planda kendi paletini uygulaması gerekir.

Ortam palette özelliğinden kullanmayan eski kapsayıcıları WM_QUERYNEWPALETTE ve WM_PALETTECHANGED iletileri gönderir. Bir denetimi geçersiz kılabilirsiniz `OnQueryNewPalette` ve `OnPaletteChanged` bu iletileri işlemek için.

##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Internet Explorer tarayıcı güvenlik düzeylerini ve denetimi davranışı

Bir tarayıcı için güvenlik düzeyi, kullanıcı tarafından yapılandırılabilir seçenekleri vardır. Web sayfaları, bir kullanıcının bilgisayarına zarar etkin içerik içerebileceğinden, tarayıcılar için güvenlik düzeyi seçeneklerini seçmesini sağlar. Tarayıcı güvenlik düzeyi uygular biçimi, bağlı olarak bir denetim hiç yüklenmemiş veya bir sertifika veya çalışma zamanında denetim indirmek depolamamayı yapmalarına izin vermek için bir uyarı iletisi görüntülenir. Internet Explorer altında yüksek, Orta ve düşük güvenlik düzeylerini ActiveX denetimlerinde davranışını aşağıda verilmiştir.

### <a name="high-safety-mode"></a>Yüksek güvenlik modu

- İmzasız denetimlerini yüklenmeyecektir.

- İmzalı denetimleri, güvenilmeyen bir sertifika görüntüler (bir kullanıcı her zaman şu andan itibaren bu sertifika sahibinin koddan güven için bir seçenek de seçebilirsiniz).

- Yalnızca güvenli olarak işaretlenmiş denetimleri kalıcı veri sahip ve/veya kodlanabilir.

### <a name="medium-safety-mode"></a>Orta güvenlik modu

- İmzasız denetimlerini yüklemeden önce bir uyarı görüntüler.

- İmzalı denetimleri güvenilmeyen bir sertifika görüntülenir.

- Denetimleri güvenli olarak işaretlenmemiş bir uyarı görüntüler.

### <a name="low-safety-mode"></a>Düşük güvenlik modu

- Denetimleri uyarı vermeden indirilir.

- Komut dosyası ve Kalıcılık uyarı vermeden oluşur.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC ActiveX Denetimleri: ActiveX Denetimini Lisanslama](../mfc/mfc-activex-controls-licensing-an-activex-control.md)

