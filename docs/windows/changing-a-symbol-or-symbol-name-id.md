---
title: Bir sembol değiştirme
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing
- vc.editors.symbol.restrictions.name
- vc.editors.symbol.changing.value
- vc.editors.symbol.restrictions.value
- vc.editors.symbol.changing.header
helpviewer_keywords:
- symbol names
- symbols [C++], names
- restrictions, symbol names
- numeric values
- symbols [C++], numeric values
- numeric values, changing symbols
- symbols [C++], value restrictions
- restrictions, symbol values
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: 7d2890c2d2c05f1ee0309446dfe2de9917f85707
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763992"
---
# <a name="changing-a-symbol"></a>Bir sembol değiştirme

Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda, geliştirme ortamı varsayılan sembol adı, örneğin, IDD_DIALOG1 atar. Kullanabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) varsayılan sembol adı değiştirmek veya zaten bir kaynakla ilişkilendirilmiş herhangi bir sembol adını değiştirmek için.

Tek bir kaynakla ilişkili semboller için de kullanabilirsiniz **özellikleri** penceresi simge değerini değiştirmek için. Kullanabileceğiniz [kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md) sembolleri bir kaynağa atanmış değerini değiştirin. Daha fazla bilgi için [atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md).

Normalde tüm sembol tanımlarını kaydedilir `Resource.h`. Ancak, bunu değiştirmeniz gerekebilir, örneğin, birden fazla kaynak dosyayla aynı dizinde çalışabilir böylece dosya adı içermelidir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="to-change-a-resources-symbol-name-id"></a>Bir kaynağın sembol adını (ID) değiştirileceğini

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), kaynağı seçin.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde **özellikleri** penceresinde, yeni bir sembol adı yazın veya mevcut simgeler listesinden **kimliği** kutusu.

   Yeni bir sembol adı yazdığınızda, değer otomatik olarak atanır.

Kullanabileceğiniz [kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md) bir kaynağa atanmış sembol adlarını değiştirmek için. Daha fazla bilgi için [atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md).

### <a name="symbol-name-restrictions"></a>Sembol adı kısıtlamaları

Sembol adı kısıtlamaları aşağıdaki gibidir:

- Tüm [sembolleri](../windows/symbols-resource-identifiers.md) uygulama kapsamında benzersiz olmalıdır. Bu, üstbilgi dosyalarında çakışan sembol tanımlarını engeller.

- Sembol adı için geçerli karakterler, A-Z, a-z, 0-9 ve alt çizgi (_) içerir.

- Sembol adları bir sayı ile başlayamaz ve 247 karakter ile sınırlıdır.

- Sembol adları boşluk içeremez.

- Sembol adları büyük/küçük harfe duyarlı değildir, ancak ilk sembol tanımı durumu korunur. Sembolleri tanımlar üstbilgi dosyası, kaynaklar bir kaynak dosyasında tanımlanan başvurmak için hem kaynak derleyici/Düzenleyicisi hem de C++ programlarının tarafından kullanılır. Yalnızca kaynak derleyici/Düzenleyici tek bir sembole başvuru olarak her iki adlarını görür ancak C++ program iki ayrı sembolleri görür durumunda, iki sembol adları için farklı.

   > [!NOTE]
   > Standart sembol adı düzeni izlemeyin varsa (ID*_[keyword]) özetlenen aşağıda ve kaynak kod dosyasını derlenmeye çalışılıyor, kaynak kod derleyici bilinen bir anahtar sözcük görünüşte rastgele hatayla sonuçlanır. aynı olacak şekilde, sembol adı olur. tanı koymak güç oluşturma. Bunu önlemek için standart adlandırma şeması izliyor.

Sembol adları, kaynak veya temsil ettikleri nesne türünü belirten açıklayıcı önekleri vardır. Açıklayıcı bu ön ekler metin birleşim kimliği ile başlayın Microsoft Foundation Class Kitaplığı'nı (MFC) aşağıdaki tabloda gösterilen simge adlandırma kurallarını kullanır.

|Kategori|Ön eki|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|------------|---------|
|Kaynaklar|IDR_ IDD_ IDC_ IDI_ IDB_|Hızlandırıcı veya menü (ve ilişkili ya da özel kaynaklar) imleç simgesi bit eşlem iletişim kutusu|
|Menü öğeleri|ID_|Menü öğesi|
|Komutlar|ID_|Komut|
|Denetimleri ve alt pencereler|IDC_|Denetim|
|Dizeler|IDS_|Dize tablosunda dize|
|MFC|AFX_|Önceden tanımlanmış MFC sembolleri için ayrılmış|

## <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>Bir tek bir kaynak veya nesne atanmış bir simge değerini değiştirmek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), kaynağı seçin.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde **özellikleri** penceresinde, tür sembol adı ve ardından bir eşittir işareti ve bir tamsayı olarak **kimliği** kutusunda, örneğin:

    ```
    IDC_EDITNAME=5100
    ```

Yeni değer proje kaydettiğinizde sembol üstbilgi dosyasında depolanır. Sembol adı kimliği kutusuna görünür kalır; Bunlar doğrulandıktan sonra eşittir işareti ve değer görüntülenmez.

### <a name="symbol-value-restrictions"></a>Sembol değeri kısıtlamaları

Sembol değeri için normal şekilde ifade edilen herhangi bir tamsayı olabilir # önişlemci yönergeleri define. Sembol değerlerinin bazı örnekleri aşağıda verilmiştir:

```
18
4001
0x0012
-3456
```

Kaynaklar (Hızlandırıcıları, bit eşlemler, işaretçiler, iletişim kutuları, simgeler, menüler, dize tabloları ve sürüm bilgileri) için Sembol değerlerini ondalık sayı 0 ile 32.767 aralığında olmalıdır (ancak onaltılık olamaz). İletişim kutusu denetimleri veya dize tablosunda, tek tek dizeler gibi kaynaklar bölümleri için Sembol değerlerini 65,534 0 veya -32.768 ile 32.767 olabilir.

Kaynak sembolleri 16 bit sayılardır. Bunları işaretli veya işaretsiz girebilirsiniz, ancak bunlar dahili olarak işaretsiz tamsayılar kullanılır. Bu nedenle negatif sayılar, karşılık gelen pozitif değerlerine dönüştürme.

Sembol değerlerinin bazı kısıtlamalar şunlardır:

- Visual Studio geliştirme ortamını ve MFC bazı aralık sayısı, özel amaçlar için kullanın. MFC tarafından tüm sayılar en anlamlı biti ayarlanmış (-32.768 -1 veya 32.768 için 65,534, oturum bağlı olarak) ile ayrılmıştır.

- Diğer sembol dizeleri kullanan bir sembol değer tanımlayamazsınız. Örneğin, aşağıdaki simge tanımı desteklenmez:

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- Önişlemci makroları değer tanımlarla bağımsız değişkenlerle birlikte kullanamazsınız. Örneğin:

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

   ne bağımsız olarak geçerli bir ifade değil `ID` derleme zamanında değerlendirilir.

- Uygulamanızın ifadeleri ile tanımlanan sembolleri içeren mevcut bir dosya olabilir. Salt okunur semboller symbols ekleme hakkında daha fazla bilgi için bkz. [kullanılarak paylaşılan (salt okunur) veya hesaplanan sembolleri](../windows/including-shared-read-only-or-calculated-symbols.md).

Aralık sayısı hakkında daha fazla bilgi için bkz. [TN023: Standart MFC kaynakları](../mfc/tn023-standard-mfc-resources.md).

## <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>Kaynak sembol başlık dosyası adını değiştirmek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasını sağ tıklatın ve seçin [kaynak içerikleri](../windows/resource-includes-dialog-box.md) kısayol menüsünden.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde **sembol başlık dosyası** içerme dosyası için yeni bir ad yazın.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)<br/>
[Kaynak Sembollerini Görüntüleme](../windows/viewing-resource-symbols.md)<br/>
