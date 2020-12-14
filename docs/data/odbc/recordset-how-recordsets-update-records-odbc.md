---
description: 'Kayıt kümesi: kayıt kümelerinin kayıtları güncelleştirme (ODBC) hakkında daha fazla bilgi'
title: 'Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
ms.openlocfilehash: c5304bd30093a203efbd9ee4d02d07b2d35b4b18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304512"
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bir veri kaynağından kayıtları seçme yeteneğinin yanı sıra, kayıt kümeleri (isteğe bağlı olarak) seçili kayıtları güncelleştirebilir veya silebilir veya yeni kayıtlar ekleyebilir. Bir kayıt kümesinin updateözelliği olan üç faktör belirlenir: bağlı veri kaynağının güncelleştirilebilir olup olmadığı, bir kayıt kümesi nesnesi oluştururken belirttiğiniz seçenekler ve oluşturulan SQL.

> [!NOTE]
> Nesnenizin temel aldığı SQL, `CRecordset` kayıt kümenizin güncelleyebilme özelliğini etkileyebilir. Örneğin, SQL 'niz bir JOIN veya **Group By** yan tümcesi IÇERIYORSA, MFC UPDATEÖZELLIĞINI false olarak ayarlar.

> [!NOTE]
> Bu konu, `CRecordset` toplu satır yakalamanın uygulanmadığı, öğesinden türetilmiş nesneler için geçerlidir. Toplu satır getirme kullanıyorsanız, bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Bu konuda aşağıdakiler açıklanmaktadır:

- [Kayıt kümesi güncellemede](#_core_your_role_in_recordset_updating) ve Framework 'ün sizin için yaptığı roldür.

- [Kayıt kümesi bir düzenleme arabelleği](#_core_the_edit_buffer) ve [Dinamik kümeler ile anlık görüntüler arasındaki farklılıklar](#_core_dynasets_and_snapshots).

[Kayıt kümesi: AddNew, düzenleme ve silme işi (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) , kayıt kümesinin görünüm noktasından bu işlevlerin eylemlerini açıklar.

[Kayıt kümesi: güncelleştirmeler hakkında daha fazla bilgi (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md) , işlemlerin güncelleştirmeleri nasıl etkilediğini, bir kayıt kümesinin veya kaydırmanın sürmekte olan güncelleştirmeleri nasıl etkilediğini ve diğer kullanıcıların güncelleştirmeleriyle nasıl etkileşim kuracağını açıklayarak kayıt kümesi güncelleştirme hikayesini tamamlar.

## <a name="your-role-in-recordset-updating"></a><a name="_core_your_role_in_recordset_updating"></a> Kayıt kümesi güncellemede rolünüz

Aşağıdaki tabloda, kayıt kümelerini kullanarak kayıtları ekleme, düzenleme veya silme, çerçevenin sizin için ne yaptığı hakkında daha fazla yer verilmiştir.

### <a name="recordset-updating-you-and-the-framework"></a>Kayıt kümesi güncelleştirme: siz ve Framework

|Siz|Framework|
|---------|-------------------|
|Veri kaynağının güncelleştirilebilir olup olmadığını (veya appdable) belirleme.|Veri kaynağının updateyetenekleri veya appenmaliyet testi için [CDatabase](../../mfc/reference/cdatabase-class.md) üye işlevlerini sağlar.|
|Güncelleştirilebilir bir kayıt kümesi açın (herhangi bir tür).||
|Kayıt kümesinin, veya gibi güncelleştirme işlevleri çağırarak güncelleştirilebilir olup olmadığını belirleme `CRecordset` `CanUpdate` `CanAppend` .||
|Kayıt eklemek, düzenlemek ve silmek için kayıt kümesi üye işlevlerini çağırın.|Kayıt kümesi nesneniz ve veri kaynağı arasında veri alışverişi yapmak için olan mekanizması yönetir.|
|İsteğe bağlı olarak, güncelleştirme işlemini denetlemek için işlemleri kullanın.|`CDatabase`İşlemleri desteklemek için üye işlevleri sağlar.|

İşlemler hakkında daha fazla bilgi için bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="the-edit-buffer"></a><a name="_core_the_edit_buffer"></a> Düzenleme arabelleği

Toplu olarak alınan bir kayıt kümesinin alan veri üyeleri, geçerli kayıt olan bir kayıt içeren bir düzenleme arabelleği olarak görev yapar. Güncelleştirme işlemleri bu arabelleği geçerli kayıt üzerinde çalışacak şekilde kullanır.

- Bir kayıt eklediğinizde, düzenleme arabelleği yeni bir kayıt oluşturmak için kullanılır. Kayıt eklemeyi bitirdiğinizde, daha önce geçerli olan kayıt yeniden geçerli olur.

- Bir kaydı güncelleştirdiğinizde (düzenlerken), kayıt kümesinin alan veri üyelerini yeni değerlere ayarlamak için düzenleme arabelleği kullanılır. Güncelleştirme tamamlandığında, güncelleştirilmiş kayıt hala geçerli olur.

[AddNew](../../mfc/reference/crecordset-class.md#addnew) veya [Edit](../../mfc/reference/crecordset-class.md#edit)'i çağırdığınızda, geçerli kayıt depolanır, böylece daha sonra gerektiğinde geri yüklenebilir. [Sil](../../mfc/reference/crecordset-class.md#delete)' i çağırdığınızda geçerli kayıt depolanmaz, ancak silindi olarak işaretlenir ve başka bir kayda kaydırmanız gerekir.

> [!NOTE]
> Düzenleme arabelleğinin kayıt silme bölümünde hiçbir rol yok. Geçerli kaydı sildiğinizde, kayıt silindi olarak işaretlenir ve farklı bir kayda kayana kadar kayıt kümesi "kayıt üzerinde değil" olur.

## <a name="dynasets-and-snapshots"></a><a name="_core_dynasets_and_snapshots"></a> Dinamik kümeler ve anlık görüntüler

[Dinamik kümeler](../../data/odbc/dynaset.md) , kayda kaydırma yaparken bir kaydın içeriğini yeniler. [Anlık görüntüler](../../data/odbc/snapshot.md) kayıtların statik temsilleridir, bu nedenle yeniden [sorgulama](../../mfc/reference/crecordset-class.md#requery)çağrısı yapmadığınız takdirde bir kaydın içeriği yenilenmez. Dinamik kümeler 'ın tüm işlevlerini kullanmak için, doğru ODBC API desteğinin düzeyine uyan bir ODBC sürücüsü ile çalışmanız gerekir. Daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md) ve [Dynaset](../../data/odbc/dynaset.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: AddNew, düzenleme ve silme Işi (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)
