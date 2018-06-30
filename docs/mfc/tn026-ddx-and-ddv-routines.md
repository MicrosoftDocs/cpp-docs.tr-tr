---
title: 'TN026: DDX ve DDV rutinleri | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DDX
- DDV
dev_langs:
- C++
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91b5d1a770dfd26db96b71179d3775003d7205c4
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122934"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX ve DDV Rutinleri

> [!NOTE]
> İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.

Bu Not iletişim kutusu veri değişimi (DDX) ve iletişim kutusu veri doğrulama (DDV) mimarisini açıklar. Ayrıca bir COleDBRecordView veya DDV_ yordamı yazma biçimini ve, yordamları kullanacak şekilde ClassWizard nasıl genişletebileceğini açıklar.

## <a name="overview-of-dialog-data-exchange"></a>İletişim kutusu veri değişimi genel bakış

Tüm iletişim kutusu veri işlevleri C++ kodu ile yapılır. Özel kaynaklar veya Sihirli makroları yok. Kalp mekanizmasının bir iletişim kutusu veri değişimi mu her iletişim sınıfta geçersiz sanal işlev ve doğrulama ' dir. Ayrıca, bu formda her zaman bulunur:

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

Özel biçim AFX açıklamaları bulun ve bu işlev içindeki kod düzenlemek ClassWizard izin verin. ClassWizard ile uyumlu olmayan kod dışında özel biçim açıklamaları yerleştirilmelidir.

Yukarıdaki örnekte, < data_exchange_function_call > biçiminde olan:

```cpp
DDX_Custom(pDX, nIDC, field);
```

ve < data_validation_function_call > isteğe bağlıdır ve şu şekildedir:

```cpp
DDV_Custom(pDX, field, ...);
```

Birden fazla COleDBRecordView/DDV_ çifti her eklenebilir `DoDataExchange` işlevi.

'Afxdd_.h' tüm iletişim kutusu veri değişimi rutinleri ve MFC ile sağlanan iletişim kutusu veri doğrulama rutinleri listesi için bkz.

İletişim verisi olan tam olarak bunu: üye verileri `CMyDialog` sınıfı. Yapı veya benzer bir şey depolanmaz.

## <a name="notes"></a>Notlar

Bu "iletişim kutusu veri" diyoruz, tüm özellikleri türetilmiş herhangi bir sınıf olarak kullanılabilir, ancak `CWnd` ve yalnızca iletişim kutuları için sınırlı değildir.

Verilerin ilk değerleri standart C++ oluşturucuda, genellikle bir blok ile ayarlanır `//{{AFX_DATA_INIT` ve `//}}AFX_DATA_INIT` açıklamaları.

`CWnd::UpdateData` başlatma ve hata çağrısı geçici işleme işlemi `DoDataExchange`.

Çağırabilirsiniz `CWnd::UpdateData` veri değişimi ve doğrulaması gerçekleştirmek için herhangi bir zamanda. Varsayılan olarak `UpdateData`(TRUE) varsayılan olarak adlandırılan `CDialog::OnOK` işleyici ve `UpdateData`(FALSE), varsayılan olarak çağrılır `CDialog::OnInitDialog`.

DDV_ yordamı hemen COleDBRecordView yordamı için izlemeniz gereken *alan*.

## <a name="how-does-it-work"></a>Nasıl çalışır

İletişim kutusu veri kullanmak için aşağıdakileri anlamanız gerekmez. Ancak, bunun arka planda nasıl çalıştığını anlamak, kendi exchange veya doğrulama yordamı yazmanıza yardımcı olur.

`DoDataExchange` Üye işlevi çok benzer olduğunu `Serialize` üye işlevi - olmasından almayı veya veri ayarlamayı/dış bir formdan sorumlu (Bu durumda denetimleri bir iletişim kutusunda) / sınıf üye verileri için. *PDX* parametre veri değiş tokuşu yapmak için bağlam ve benzer `CArchive` parametresi `CObject::Serialize`. *PDX* (bir `CDataExchange` nesnesi) çok benzer bayrak yönüne sahip `CArchive` bir yön bayrağı vardır:

- Varsa `!m_bSaveAndValidate`, sonra denetimlere veri durumu yükleyin.

- Varsa `m_bSaveAndValidate`, ardından veri durumu denetimlerini ayarlayın.

Doğrulama yalnızca oluşur zaman `m_bSaveAndValidate` ayarlanır. Değeri `m_bSaveAndValidate` BOOL parametresi tarafından belirlenen `CWnd::UpdateData`.

Var olan üç diğer ilginç `CDataExchange` üyeleri:

- `m_pDlgWnd`: Denetimleri içerir penceresi (genellikle bir iletişim kutusu). 'This' geçirmek zorunda kalmaktan COleDBRecordView ve DDV_ genel işlevler arayanlar önlemek için her DDX/DDV yordamına budur.

- `PrepareCtrl`, ve `PrepareEditCtrl`: bir iletişim kutusu denetim veri değişimi için hazırlar. Doğrulama başarısız olursa odağı ayarlamak için bu denetimin işleyicisi depolar. `PrepareCtrl` Düzen olmayan denetimler için kullanılır ve `PrepareEditCtrl` düzenleme denetimleri için kullanılır.

- `Fail`: Giriş hatası kullanıcıya uyarı bir ileti kutusu getiren sonra çağrılır. Bu yordam son denetim odağı geri yükler (son çağrısı `PrepareCtrl` veya `PrepareEditCtrl`) ve bir özel durum. Bu üye işlevi COleDBRecordView ve DDV_ yordamlarından çağrılabilir.

## <a name="user-extensions"></a>Kullanıcı Uzantıları

Varsayılan DDX/DDV mekanizması genişletmek için birkaç yolu vardır. Şunları yapabilirsiniz:

- Yeni veri türleri ekleyin.

    ```cpp
    CTime
    ```

- Yeni exchange yordamları (COleDBRecordView) ekleyin.

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- Yeni doğrulama yordamları (DDV_) ekleyin.

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- Rastgele ifadeleri doğrulama yordamları geçirin.

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > Bu tür rasgele ifadeleri ClassWizard tarafından düzenlenemez ve bu nedenle özel biçim açıklamaları dışında taşınması gereken (/ / {{AFX_DATA_MAP(CMyClass)).

Sahip `DoDialogExchange` üye işlevi bilgi almak veya herhangi başka geçerli C++ deyimleri ile intermixed değişimi ve doğrulaması işlev çağrılarını içerir.

```cpp
//{{AFX_DATA_MAP(CMyClass)
DDX_Check(pDX, IDC_SEX, m_bFemale);
DDX_Text(pDX, IDC_EDIT1, m_age);
//}}AFX_DATA_MAP
if (m_bFemale)
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);
else
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);
```

> [!NOTE]
> Yukarıda gösterildiği gibi bu tür kod ClassWizard tarafından düzenlenemez ve yalnızca özel biçim yorumları dışında kullanılmalıdır.

## <a name="classwizard-support"></a>ClassWizard desteği

ClassWizard, kendi COleDBRecordView ve DDV_ yordamlarını ClassWizard kullanıcı arabirimi ile tümleştirmenize olanak tanıyarak DDX/DDV özelleştirmeleri kümesini destekler. Bir proje veya çok sayıda proje belirli DDX ve DDV rutinleri yeniden kullanmayı planlıyorsanız Bunun yapılması yalnızca faydalı maliyetidir.

Bunu yapmak için özel girişler DDX içinde oluşturulur. CLW (Visual C++ önceki sürümleri depolanır bu bilgileri APSTUDIO içinde. INI) veya projenizin. CLW dosyası. Özel girişleri olabilir ya da projenizin [genel bilgi] bölümünü girilen. CLW dosya veya DDX [ExtraDDX] bölümünde. \Program Visual Studio\Visual C ++ \bin dizinine dosyasında CLW. DDX oluşturmanız gerekebilir. Zaten yoksa CLW dosyası. Yalnızca belirli projede özel COleDBRecordView/DDV_ yordamları kullanmayı planlıyorsanız, girişleri projenizin [genel bilgi] bölümüne ekleyin. Bunun yerine CLW dosya. Birçok projelerde yordamları kullanmayı planlıyorsanız, girişleri DDX [ExtraDDX] bölümüne ekleyin. CLW.

Bu özel girişleri genel biçimi şöyledir:

> ExtraDDXCount =*n*

Burada *n* ExtraDDX sayısı? izlemenizi şeklinde satırlarını

> ExtraDDX? =*anahtarları*; *vb anahtarları*; *istemi*; *türü*; *initValue*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

nerede? 1 - bir sayıdır *n* tanımlanıyorsa listesinde hangi DDX türünü belirten.

Her bir alan ';' karakteriyle ayrılmış. Alanları ve bunların amacı, aşağıda açıklanmıştır.

- *Anahtarları*

  Bu değişken türü için hangi iletişim kutusu denetimleri belirten tek karakter listesinin izin verilir.

  |Karakter|İzin verilen denetimi|
  |-|-|
  E | Düzenleme
  C | iki durumlu onay kutusu
  c | üç durumlu onay kutusu
  R | bir gruptaki ilk radyo düğmesi
  L | nonsorted liste kutusu
  l | Sıralı liste kutusu
  M | Birleşik giriş kutusu (öğesiyle Düzen)
  N | nonsorted açılan liste
  n | sıralanmış açılan liste
  1. | DDX ekleme listesi head için eklenip eklenmeyeceğini (kuyruk için varsayılan ekleme) Bu genellikle 'Denetim' özelliği aktarım DDX yordamları için kullanılır.

- *vb anahtarları*

  Bu alan yalnızca 16 bit üründe VBX denetimleri (VBX denetimleri 32-bit ürününde desteklenmez) için kullanılır.

- *Sor*

  Özellik birleşik giriş kutusu içinde (tırnak işaretleri olmadan) yerleştirmek için dize

- *Türü*

  Üstbilgi dosyasında yayma türünün tek tanımlayıcısı. Bizim örneğimizde DDX_Time ile bu CTime için ayarlanır.

- *vb anahtarları*

  ' In bu sürümünde kullanılmaz ve her zaman boş olmalıdır

- *initValue*

  İlk değer: 0 veya boş. Boş ise, hiçbir başlatma satırı uygulama dosyasının //{{AFX_DATA_INIT bölümünde yazılır. C++ nesneleri için boş bir girdiyi kullanılmalıdır (gibi `CString`, `CTime`, vb.) doğru başlatma garanti oluşturucular sahip.

- *DDX_Proc*

  COleDBRecordView yordamı için tek tanımlayıcı. C++ işlev adı "COleDBRecordView" ile başlaması gerekir, ancak "COleDBRecordView" < DDX_Proc > tanımlayıcıda dahil etmeyin. Yukarıdaki örnekte, zaman < DDX_Proc > tanımlayıcısı olacaktır. Uygulama dosyasında işlev çağrısı yazdığında ClassWizard {{AFX_DATA_MAP bölümünde, bu ekler bu adı COleDBRecordView, böylece DDX_Time ulaşan için.

- *Açıklama*

  Bu DDX değişkenle iletişim kutusunda göstermek için bir açıklama. DDX/DDV çifti tarafından gerçekleştirilen işlem açıklayan buraya ve genellikle bir şey sağlamak istediğiniz herhangi bir metin yerleştirin.

- *DDV_Proc*

  Giriş DDV kısmı isteğe bağlıdır. Tüm DDX yordamları karşılık gelen DDV rutinleri vardır. Genellikle, doğrulama aşamasını Aktarımı'nın ayrılmaz bir parçası dahil etmek daha uygundur. Herhangi bir parametre DDV alışkanlık gerektirmeyen zaman ClassWizard DDV rutinleri hiçbir parametre olmadan desteklemediğinden bu genellikle durumdur.

- *arg*

  DDV_ yordamı için tek tanımlayıcı. C++ işlev adı "DDV_" ile başlaması gerekir, ancak "COleDBRecordView" < DDX_Proc > tanımlayıcıda içermez.

  *arg* 1 veya 2 DDV args tarafından izlenir:

   - *promptN*

     Düzenleme öğesi (& Hızlandırıcı için) yukarıdaki yerleştirmek için dize.

   - *fmtN*

     Biçim karakteri birini arg türü için:

     |Karakter|Tür|
     |-|-|
     d | int
     u | unsigned int
     D | int uzun (diğer bir deyişle, uzun)
     U | uzun imzasız (DWORD)
     F | float
     F | çift
     s | dize

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)  
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)  
