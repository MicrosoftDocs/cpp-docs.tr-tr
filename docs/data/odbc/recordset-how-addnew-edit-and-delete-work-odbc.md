---
title: 'Kayıt kümesi: Nasıl AddNew, düzenleme ve silmenin çalışması (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- AddNew method
- ODBC recordsets [C++], deleting records
- records [C++], deleting in recordsets
- data in recordsets [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dbbf224797bd7d2eed2b085a6a7dd8eb1865de1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>Kayıt Kümesi: AddNew, Düzenleme ve Silmenin Çalışması (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda açıklanmaktadır nasıl `AddNew`, **Düzenle**, ve **silmek** sınıfının üye işlevleri `CRecordset` çalışır. Kapsanan konular şunlardır:  
  
-   [Kayıt eklemeler nasıl çalışır](#_core_adding_a_record)  
  
-   [Eklenen kayıtların görünürlüğü](#_core_visibility_of_added_records)  
  
-   [Kayıtları düzenleme nasıl çalışır](#_core_editing_an_existing_record)  
  
-   [Kayıtların işleri nasıl silinir](#_core_deleting_a_record)  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Ek olarak, okumak isteyebilirsiniz [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md), RFX karşılık gelen rol güncelleştirme işlemlerinde açıklar.  
  
##  <a name="_core_adding_a_record"></a>Kayıt ekleme  

 Bir kayıt kümesine yeni bir kayıt ekleme içerir kayıt kümesinin çağırma [AddNew](../../mfc/reference/crecordset-class.md#addnew) yeni kayıttaki alan veri üyeleri değerleri ayarlama ve çağırma üye işlevi [güncelleştirme](../../mfc/reference/crecordset-class.md#update) yazmak için üye işlevi veri kaynağı kaydı.  
  
 Arama için bir önkoşul olarak `AddNew`, kayıt kümesi salt okunur olarak açılmış olmalıdır değil. `CanUpdate` Ve `CanAppend` üye işlevleri bu koşulları belirlemenize olanak sağlar.  
  
 Çağırdığınızda `AddNew`:  
  
-   Kayıt düzenleme arabelleği içinde depolanır, bu işlemi iptal ederseniz içeriğinin geri yüklenebilmesi için.  
  
-   Alan veri üyeleri değişiklikleri daha sonra bunları algılamak mümkün olacak şekilde işaretlenir. Üyeleri de işaretlenmiş alan verileri (değişmeden) temizlemek ve Null değerine ayarlayın.  
  
 Çağırdıktan sonra `AddNew`düzenleme arabelleği yeni temsil eder, kayıt değerleri ile doldurulması için hazır boş. Bunu yapmak için el ile değerlerini atayarak ayarlayın. Bir alan için gerçek bir veri değeri belirtmek yerine çağırabilirsiniz `SetFieldNull` Null değeri belirtmek için.  
  
 Değişikliklerinizi uygulamak için arama **güncelleştirme**. Çağırdığınızda **güncelleştirme** yeni kayıt için:  
  
-   ODBC sürücüsü destekliyorsa **:: SQLSetPos** ODBC API işlevi, MFC veri kaynağı kaydı eklemek için işlevi kullanır. İle **:: SQLSetPos**, MFC ekleyebileceğiniz bir kaydı daha verimli bir şekilde bir SQL deyimi oluşturmak ve işlemek olmadığından.  
  
-   Varsa **:: SQLSetPos** olamaz kullanıldığında, MFC şunları yapar:  
  
    1.  Hiçbir değişiklik algılanırsa, **güncelleştirme** hiçbir şey yapmaz ve 0 döndürür.  
  
    2.  Değişiklikler, varsa **güncelleştirme** bir SQL yapıları **Ekle** deyimi. Tüm kirli alan veri üyeleri tarafından temsil edilen sütunlar listelenen **Ekle** deyimi. Bir sütun eklenmesi zorlamak için arama [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) üye fonksiyonu:  
  
        ```  
        SetFieldDirty( &m_dataMember, TRUE );  
        ```  
  
    3.  **Güncelleştirme** yeni kaydı kaydeder — **Ekle** deyimi yürütüldüğünde ve bir işlem devam ediyor sürece kaydı için veri kaynağı (ve kayıt kümesi, bir anlık görüntü değilse) tabloda taahhüt eder.  
  
    4.  Saklı kayıt düzenleme ara geri yüklenir. Önce geçerli kayıt `AddNew` çağrıdır yeniden olup olmamasına bakılmaksızın geçerli **Ekle** deyimi başarıyla yürütüldü.  
  
    > [!TIP]
    >  Yeni bir kayıt tam denetim için aşağıdaki yaklaşımı: değerlere sahip ve Null çağırarak kalacak herhangi bir alan açıkça ayarlanmış herhangi bir alan değerleri ayarlamak `SetFieldNull` alan ve parametresi için bir işaretçi ile **TRUE**  (varsayılan). Bir alan veri kaynağı için çağrı yazılmaz emin olmak istiyorsanız `SetFieldDirty` alan ve parametresi için bir işaretçi ile **yanlış**ve alanın değerini değiştirmeyin. Bir alan Null olmasına izin verilip verilmediğini belirlemek için arama `IsFieldNullable`.  
  
    > [!TIP]
    >  Kayıt kümesi veri üyeleri değeri değiştirdiğinizde algılamak için MFC kullanan bir **PSEUDO_NULL** kayıt kümesinde depolayabilir her bir veri türü için uygun değer. Açıkça bir alan ayarlanmalıdır **PSEUDO_NULL** de çağırmanız gerekir değeri ve alan gerçekleşir zaten Null, işaretlenecek `SetFieldNull`, ilk parametre alanında adresini geçirme ve **FALSE**ikinci parametre olarak.  
  
##  <a name="_core_visibility_of_added_records"></a>Eklenen kayıtların görünürlüğü  
 Ne zaman eklenen kayıt kümenize görünebilir mi? Eklenen kayıtları bazen görünür ve bazen bağlı olarak iki şey görünür değildir:  
  
-   Sürücünüzün neyi yapabilir.  
  
-   Framework yararlanabilir.  
  
 ODBC sürücüsü destekliyorsa **:: SQLSetPos** ODBC API işlevi, MFC kayıtları eklemek için işlevi kullanır. İle **:: SQLSetPos**, kayıtları herhangi güncelleştirilebilir MFC kayıt kümesine görünür eklenir. İşlev için desteği olmadan kayıtları görünür değildir ve çağırmalısınız eklenen **Requery** bunları görmek için. Kullanarak **:: SQLSetPos** ayrıca daha etkilidir.  
  
##  <a name="_core_editing_an_existing_record"></a>Varolan bir kaydı düzenleme  
 Bir kayıt kümesinde varolan kaydı düzenleme içerir kayıt kümesinin çağırma kayda kaydırma [Düzenle](../../mfc/reference/crecordset-class.md#edit) yeni kayıttaki alan veri üyeleri değerleri ayarlama ve çağırma üye işlevi [güncelleştirme](../../mfc/reference/crecordset-class.md#update)veri kaynağına değiştirilen kaydı yazmak için üye işlevi.  
  
 Arama için bir önkoşul olarak **Düzenle**, kayıt kümesinin güncelleştirilebilir ve bir kayıt üzerinde olmalıdır. `CanUpdate` Ve `IsDeleted` üye işlevleri bu koşulları belirlemenize olanak sağlar. Geçerli kayıt de zaten silinmemiş gerekir ve kayıt kümesinde kayıtları olmalıdır (her ikisi de `IsBOF` ve `IsEOF` 0 döndürür).  
  
 Çağırdığınızda **Düzenle**, kayıt düzenleme arabelleği (geçerli kayıt) içinde depolanır. Saklı kaydın değerleri daha sonra herhangi bir alan değişip değişmediğini belirlemek için kullanılır.  
  
 Çağırdıktan sonra **Düzenle**, düzenleme arabelleği hala geçerli kaydı temsil eder, ancak artık alan veri üyeleri için değişiklikleri kabul etmek üzere hazırdır. Kayıt değiştirmek için el ile düzenlemek istediğiniz herhangi bir alan veri üyeleri değerlerini ayarlayın. Bir alan için gerçek bir veri değeri belirtmek yerine çağırabilirsiniz `SetFieldNull` Null değeri belirtmek için. Değişikliklerinizi uygulamak için arama **güncelleştirme**.  
  
> [!TIP]
>  İşyeri dışında almak için `AddNew` veya **Düzenle** modu, çağrı **taşıma** parametresiyle **AFX_MOVE_REFRESH**.  
  
 Arama için bir önkoşul olarak **güncelleştirme**, kayıt kümesi boş olmamalı ve geçerli kayıt silinmemiş gerekir. `IsBOF`, `IsEOF`, ve `IsDeleted` hepsi 0 döndürmelidir.  
  
 Çağırdığınızda **güncelleştirme** düzenlenen kaydı için:  
  
-   ODBC sürücüsü destekliyorsa **:: SQLSetPos** ODBC API işlevi, MFC kaydı veri kaynağında güncelleştirmek için işlevi kullanır. İle **:: SQLSetPos**, iki farklı ise kayıt sunucu üzerinde güncelleştirme sunucuda karşılık gelen kaydıyla, düzenleme arabelleği sürücü karşılaştırır. İle **:: SQLSetPos**, MFC güncelleştirebilirsiniz bir kaydı daha verimli bir şekilde bir SQL deyimi oluşturmak ve işlemek olmadığından.  
  
     veya  
  
-   Varsa **:: SQLSetPos** olamaz kullanıldığında, MFC şunları yapar:  
  
    1.  Herhangi bir değişiklik olduysa **güncelleştirme** hiçbir şey yapmaz ve 0 döndürür.  
  
    2.  Değişiklikler, varsa **güncelleştirme** bir SQL yapıları **güncelleştirme** deyimi. Listelenen sütunlar **güncelleştirme** ifadesi, değişen alan veri üyeleri dayalı.  
  
    3.  **Güncelleştirme** değişiklikleri kaydeder — yürütür **güncelleştirme** deyimi — ve kayıt veri kaynağında değiştirilir, ancak kaydedilmez IF işlem devam ediyor (bkz [işlem: bir işlem gerçekleştirme bir kayıt kümesi (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) işlem güncelleştirme nasıl etkilediği hakkında bilgi için). ODBC da değişir kaydı bir kopyasını tutar.  
  
    4.  İşlem için aksine `AddNew`, **Düzenle** işlemi saklı kayıt geri değil. Düzenlenmiş kayıt geçerli kayıt olarak yerinde kalır.  
  
    > [!CAUTION]
    >  Bir kayıt kümesi çağırarak güncelleştirmek hazırlama ne zaman **güncelleştirme**, kümenizin tablonun birincil anahtarı oluşturan yapmadan tüm sütunları içeren ilgilenebilmek (veya tüm sütunları herhangi benzersiz dizin tablosu veya yeterli sütun benzersiz olarak Satır tanımlayın). Bazı durumlarda, framework yalnızca kümenize seçili sütun güncelleştirmek için tablodaki hangi kaydı tanımlamak için kullanabilirsiniz. Tüm gerekli sütunları, tabloda birden çok kayıt güncelleştirilebilir. Bu durumda, çağırdığınızda çerçeve özel durumlar atar **güncelleştirme**.  
  
    > [!TIP]
    >  Çağırırsanız `AddNew` veya **Düzenle** ya da işlev daha önce ancak önce çağrılan sonra çağrısı **güncelleştirme**, düzenleme arabelleği saklı kaydıyla yeni veya düzenlenmiş kaydında değiştirme yenilenir devam ediyor. Bu davranışı iptal etmek için bir yöntem sunar bir `AddNew` veya **Düzenle** ve yeni bir tane başlayın: ilerleme içinde kaydı hatalı olduğunu belirlerseniz, yalnızca çağrısı **Düzenle** veya `AddNew` yeniden.  
  
##  <a name="_core_deleting_a_record"></a>Kayıt silme  
 Kayıt kaydırma ve kayıt kümesinin çağırma ilgilidir kayıt kümesinden bir kaydı silme [silmek](../../mfc/reference/crecordset-class.md#delete) üye işlevi. Farklı `AddNew` ve **Düzenle**, **silmek** eşleşen bir çağrı gerektirmez **güncelleştirme**.  
  
 Arama için bir önkoşul olarak **silmek**, kayıt kümesinin güncelleştirilebilir olmalıdır ve bir kayıt üzerinde olmalıdır. `CanUpdate`, `IsBOF`, `IsEOF`, Ve `IsDeleted` üye işlevleri bu koşulları belirlemenize olanak sağlar.  
  
 Çağırdığınızda **silmek**:  
  
-   ODBC sürücüsü destekliyorsa **:: SQLSetPos** ODBC API işlevi, MFC veri kaynağı kaydını silmek için işlevi kullanır. Kullanarak **:: SQLSetPos** SQL kullanmaktan genellikle daha verimli olur.  
  
     veya  
  
-   Varsa **:: SQLSetPos** olamaz kullanıldığında, MFC şunları yapar:  
  
    1.  Düzenleme arabelleği geçerli kayıt olarak yedeklenmez `AddNew` ve **Düzenle**.  
  
    2.  **Silme** bir SQL yapıları **silmek** kaydını kaldırır deyimi.  
  
         Düzenleme arabelleği geçerli kayıt olarak depolanmaz `AddNew` ve **Düzenle**.  
  
    3.  **Silme** silme işlemini tamamlar — yürütür **silmek** deyimi. Kaydı veri kaynağında silindi olarak işaretlenir ve kaydı bir anlık görüntü ODBC içinde ise.  
  
    4.  Hala alan veri üyeleri kümesi silinmiş kaydın değerlerdir ancak Null ve kayıt kümesinin alan veri üyeleri işaretlenir `IsDeleted` üye işlevi sıfır olmayan bir değer döndürür.  
  
    > [!NOTE]
    >  Bir kayıt sildikten sonra yeni kayıttaki verilerle düzenleme arabelleği yeniden doldurmak için başka bir kayda gitmeniz gerekir. Çağırmak için bir hata olduğunu **silmek** yeniden veya çağırmak için **Düzenle**.  
  
 Güncelleştirme işlemlerinde kullanılan SQL deyimleri hakkında daha fazla bilgi için bkz: [SQL](../../data/odbc/sql.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Güncelleştirmeler hakkında daha fazla (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md)   
 [Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)