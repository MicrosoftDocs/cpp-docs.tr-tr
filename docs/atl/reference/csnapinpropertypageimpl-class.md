---
title: CSnapInPropertyPageImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CSnapInPropertyPageImpl
- ATLSNAP/ATL::CSnapInPropertyPageImpl::CancelToClose
- ATLSNAP/ATL::CSnapInPropertyPageImpl::Create
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnApply
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnHelp
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnKillActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnQueryCancel
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnReset
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnSetActive
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardBack
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardFinish
- ATLSNAP/ATL::CSnapInPropertyPageImpl::OnWizardNext
- ATLSNAP/ATL::CSnapInPropertyPageImpl::QuerySiblings
- ATLSNAP/ATL::CSnapInPropertyPageImpl::SetModified
- ATLSNAP/ATL::CSnapInPropertyPageImpl::m_psp
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, property pages
- snap-ins
- property pages, ATL
- CSnapInPropertyPageImpl class
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13714553bdf926b00bd4dd76e039d89c7f78f959
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366149"
---
# <a name="csnapinpropertypageimpl-class"></a>CSnapInPropertyPageImpl sınıfı
Bu sınıf bir ek özellik sayfası nesnesi uygulamak için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
CSnapInPropertyPageImpl : public CDialogImplBase
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::CancelToClose](#canceltoclose)|Durumunu değiştirir **Tamam** ve **iptal** düğmeler.|  
|[CSnapInPropertyPageImpl::Create](#create)|Yeni oluşturulan başlatır `CSnapInPropertyPageImpl` nesnesi.|  
|[CSnapInPropertyPageImpl::OnApply](#onapply)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır **şimdi Uygula** bir sihirbaz türü özellik sayfası kullanırken düğmesi.|  
|[CSnapInPropertyPageImpl::OnHelp](#onhelp)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır **yardımcı** bir sihirbaz türü özellik sayfası kullanırken düğmesi.|  
|[CSnapInPropertyPageImpl::OnKillActive](#onkillactive)|Geçerli sayfa artık etkin olduğunda çerçevesi tarafından çağrılır.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](#onquerycancel)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır **iptal** düğmesi ve iptal gerçekleştikten önce.|  
|[CSnapInPropertyPageImpl::OnReset](#onreset)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır **sıfırlama** bir sihirbaz türü özellik sayfası kullanırken düğmesi.|  
|[CSnapInPropertyPageImpl::OnSetActive](#onsetactive)|Geçerli sayfa etkin olduğunda çerçevesi tarafından çağrılır.|  
|[CSnapInPropertyPageImpl::OnWizardBack](#onwizardback)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır **geri** bir sihirbaz türü özellik sayfası kullanırken düğmesi.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](#onwizardfinish)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır **son** bir sihirbaz türü özellik sayfası kullanırken düğmesi.|  
|[CSnapInPropertyPageImpl::OnWizardNext](#onwizardnext)|Kullanıcı tıklattığında çerçevesi tarafından çağrılır `Next` bir sihirbaz türü özellik sayfası kullanırken düğmesi.|  
|[CSnapInPropertyPageImpl::QuerySiblings](#querysiblings)|Özellik sayfası tüm sayfaları geçerli iletiyi iletir.|  
|[CSnapInPropertyPageImpl::SetModified](#setmodified)|Etkinleştirmek veya devre dışı bırakmak için çağrı **şimdi Uygula** düğmesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSnapInPropertyPageImpl::m_psp](#m_psp)|Windows **PROPSHEETPAGE** tarafından kullanılan yapısı `CSnapInPropertyPageImpl` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CSnapInPropertyPageImpl` bir ek özellik sayfası nesnesi için temel bir uygulama sağlar. Bir ek özellik sayfası, temel özellikleri birkaç farklı arabirimleri kullanılarak uygulanan ve türleri eşlenir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsnap.h  
  
##  <a name="canceltoclose"></a>  CSnapInPropertyPageImpl::CancelToClose  
 Kalıcı özellik sayfasının bir sayfa verilerde kurtarılamaz bir değişiklik yapıldıktan sonra bu işlevini çağırın.  
  
```
void CancelToClose();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev değiştirecek **Tamam** düğmesine **Kapat** ve devre dışı bırakma **iptal** düğmesi. Bu uyarılar kalıcı ve değişikliklerin bir değişikliktir kullanıcı iptal edilemez değiştirin.  
  
 `CancelToClose` Üye işlevi hiçbir şey yapmaz kalıcı olmayan özellik sayfası, kalıcı olmayan özellik sayfası sahip olmadığından bir **iptal** varsayılan düğme.  
  
##  <a name="csnapinpropertypageimpl"></a>  CSnapInPropertyPageImpl::CSnapInPropertyPageImpl  
 Oluşturan bir `CSnapInPropertyPageImpl` nesnesi.  
  
```
CSnapInPropertyPageImpl(LPCTSTR lpszTitle = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszTitle`  
 [in] Özellik sayfası başlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel alınan yapısı başlatmak için arama [CSnapInPropertyPageImpl::Create](#create).  
  
##  <a name="create"></a>  CSnapInPropertyPageImpl::Create  
 Özellik sayfası alt yapısını başlatmak için bu işlevini çağırın.  
  
```
HPROPSHEETPAGE Create();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçin bir tanıtıcı bir **PROPSHEETPAGE** yeni oluşturulan özellik sayfasını özniteliklerini içeren yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk çağırmalıdır [CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](#csnapinpropertypageimpl) bu işlevi çağrılmadan önce.  
  
##  <a name="m_psp"></a>  CSnapInPropertyPageImpl::m_psp  
 `m_psp` üyeleri özelliklerini depolamak bir yapıdır **PROPSHEETPAGE**.  
  
```
PROPSHEETPAGE m_psp;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı, oluşturulan sonra özellik sayfası görünümünü başlatmak için kullanın.  
  
 Bu grubun üyeleri listesi dahil olmak üzere bu yapı hakkında daha fazla bilgi için bkz: [PROPSHEETPAGE](http://msdn.microsoft.com/library/aa815151) Windows SDK'sındaki.  
  
##  <a name="onapply"></a>  CSnapInPropertyPageImpl::OnApply  
 Kullanıcı tıkladığında bu üye işlev çağrılır **Tamam** veya **şimdi Uygula** düğmesi.  
  
```
BOOL OnApply();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değişiklikleri kabul edilirse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Önce `OnApply` çağrılabilir çerçevesi tarafından çağrıldı gerekir `SetModified` ve kendi parametre kümesine **doğru**. Bu etkinleştirecek **şimdi Uygula** kullanıcı özellik sayfasında bir değişiklik yapar hemen düğmesi.  
  
 Programınızı geçen kullanıcı tıklattığında hangi eylemini belirtmek üzere bu üye işlevi geçersiz kılma **şimdi Uygula** düğmesi. Geçersiz kılarken işlevi döndürmelidir **TRUE** değişiklikleri kabul etmek için ve **FALSE** etkili değişiklikler engellemek için.  
  
 Varsayılan uygulaması `OnApply` döndürür **doğru**.  
  
##  <a name="onhelp"></a>  CSnapInPropertyPageImpl::OnHelp  
 Kullanıcı tıkladığında bu üye işlev çağrılır **yardımcı** özellik sayfasının düğmesini.  
  
```
void OnHelp();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfası için Yardım görüntülemek için bu üye işlevi geçersiz kılar.  
  
##  <a name="onkillactive"></a>  CSnapInPropertyPageImpl::OnKillActive  
 Sayfa artık etkin sayfa olduğunda bu üye işlev çağrılır.  
  
```
BOOL OnKillActive();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veri başarıyla güncelleştirildiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel veri doğrulama görevleri gerçekleştirmek için bu üye işlevi geçersiz kılar.  
  
##  <a name="onquerycancel"></a>  CSnapInPropertyPageImpl::OnQueryCancel  
 Kullanıcı tıkladığında bu üye işlev çağrılır **iptal** düğmesine tıklayın ve önce iptal eylemi devre dışı gerçekleştikten.  
  
```
BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İptal işlemine izin vermek için sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Program alır kullanıcı tıklattığında bir eylem belirtmek için bu üye işlevi geçersiz kılma **iptal** düğmesi.  
  
 Varsayılan uygulaması `OnQueryCancel` döndürür **doğru**.  
  
##  <a name="onreset"></a>  CSnapInPropertyPageImpl::OnReset  
 Kullanıcı tıkladığında bu üye işlev çağrılır **iptal** düğmesi.  
  
```
void OnReset();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrıldığında, daha önce tıklayarak kullanıcı tarafından yapılan tüm özellik sayfalarını değişikliklerini **şimdi Uygula** düğmesi atılır ve özellik sayfasını odağını korur.  
  
 Program alır kullanıcı tıklattığında hangi eylemini belirtmek üzere bu üye işlevi geçersiz kılma **iptal** düğmesi.  
  
##  <a name="onsetactive"></a>  CSnapInPropertyPageImpl::OnSetActive  
 Sayfa kullanıcı tarafından seçilir ve etkin sayfa haline gelir, bu üye işlev çağrılır.  
  
```
BOOL OnSetActive();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sayfa başarıyla etkin olarak ayarlandıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir sayfa etkinleştirildiğinde görevleri gerçekleştirmek için bu üye işlevi geçersiz kılar. Başka bir işlem gerçekleştirilmeden önce bu üye işlevi geçersiz kılma varsayılan sürüm çağırmanız gerekir.  
  
 Varsayılan uygulama döndürür **doğru**.  
  
##  <a name="onwizardback"></a>  CSnapInPropertyPageImpl::OnWizardBack  
 Kullanıcı tıkladığında bu üye işlev çağrılır **geri** bir Sihirbazı'nda düğmesini.  
  
```
BOOL OnWizardBack();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
-   otomatik olarak önceki sayfaya ilerletmek için 0'ı tıklatın.  
  
-   sayfa değiştirmesini engellemek için -1.  
  
 Bir sonraki dışında bir sayfaya gitmek için görüntülenecek iletişim kutusunun tanımlayıcısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı ne zaman gerçekleştirmeniz gereken bazı eylemleri belirtmek için bu üye işlevi geçersiz kılma **geri** düğmesine tıklandığında.  
  
##  <a name="onwizardfinish"></a>  CSnapInPropertyPageImpl::OnWizardFinish  
 Kullanıcı tıkladığında bu üye işlev çağrılır **son** bir Sihirbazı'nda düğmesini.  
  
```
BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sihirbaz sona erdiğinde özellik sayfasını yok, sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı ne zaman gerçekleştirmeniz gereken bazı eylemleri belirtmek için bu üye işlevi geçersiz kılma **son** düğmesine tıklandığında.  
  
##  <a name="onwizardnext"></a>  CSnapInPropertyPageImpl::OnWizardNext  
 Kullanıcı tıkladığında bu üye işlev çağrılır `Next` bir Sihirbazı'nda düğmesini.  
  
```
BOOL OnWizardNext();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
-   0-otomatik olarak sonraki sayfaya ilerleyin.  
  
-   sayfa değiştirmesini engellemek için -1.  
  
 Bir sonraki dışında bir sayfaya gitmek için görüntülenecek iletişim kutusunun tanımlayıcısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı ne zaman gerçekleştirmeniz gereken bazı eylemleri belirtmek için bu üye işlevi geçersiz kılma `Next` düğmesine tıklandığında.  
  
##  <a name="querysiblings"></a>  CSnapInPropertyPageImpl::QuerySiblings  
 Özellik sayfasında her sayfaya bir iletiyi iletmesini bu üye işlevini çağırın.  
  
```
LRESULT QuerySiblings(WPARAM wParam, LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 `wParam`  
 [in] Ek ileti bağımlı bilgileri belirtir.  
  
 `lParam`  
 [in] Ek ileti bağımlı bilgileri belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti sonraki özellik sayfası iletilmesi gereken değil, sıfır olmayan; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir sayfa sıfır olmayan bir değer döndürürse, özellik sayfasında sonraki sayfalara ileti göndermez.  
  
##  <a name="setmodified"></a>  CSnapInPropertyPageImpl::SetModified  
 Etkinleştirmek veya devre dışı bırakmak için bu üye işlevini çağırın **şimdi Uygula** düğmesi, özellik sayfasında ayarlarında uygun dış nesnesine uygulanmalıdır olup tabanlı.  
  
```
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bChanged`  
 [in] **TRUE** özellik sayfası ayarları bunlar uygulanan; en son ne zaman beri değiştirilmiş belirtmek için **FALSE** özellik sayfası ayarları uygulanmış olan veya yok sayılması gerektiğini belirtmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfasını tutar izleme hangisinin sayfaları "kirli" başka bir deyişle, kendisi için adlı özellik sayfaları **SetModified (TRUE)**. **Şimdi Uygula** düğmesi her zaman etkindir çağırırsanız **SetModified (TRUE)** sayfaları biri için. **Şimdi Uygula** düğmesi devre dışı bırakılacak çağırdığınızda **SetModified (FALSE)** yalnızca Sihirbazın diğer sayfalarını hiçbiri "kirli" ise ancak sayfaları, biri için  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
