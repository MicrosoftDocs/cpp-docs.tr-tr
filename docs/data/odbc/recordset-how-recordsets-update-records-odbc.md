---
title: 'Kayıt kümesi: Kayıtları Güncelleştirmesi (ODBC) nasıl kaydeder. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dde8f13be6039ba035a382e3c284112eeb39c0ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067148"
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.  
  
Bir veri kaynağındaki kayıtları seçmek için kendi yeteneği yanı sıra kayıt kümeleri (isteğe bağlı) güncelleştirmesi veya seçili kayıtları silebilir veya yeni kayıt ekleme. Bir kayıt kümesinin güncellenebilirliğini üç faktör belirler: bağlı veri kaynağına güncelleştirilebilir olup, bir kayıt kümesi nesnesi ve oluşturulan SQL oluştururken belirttiğiniz seçenekleri.  
  
> [!NOTE]
>  SQL, `CRecordset` nesnesi kümenizin güncellenebilirliğini etkileyebilir. Örneğin, SQL birleştirme içeriyorsa veya **GROUP BY** yan tümcesi, MFC ayarlar güncellenebilirliğini FALSE.  
  
> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
Bu konu şunları açıklar:  
  
- [Kayıt kümesi güncellemede rolünüz](#_core_your_role_in_recordset_updating) ve framework sizin için yapar.  
  
- [Kayıt düzenleme arabelleği olarak](#_core_the_edit_buffer) ve [dinamik kümeler ve anlık görüntüler arasındaki farklar](#_core_dynasets_and_snapshots).  
  
[Kayıt kümesi: Nasıl AddNew, düzenleme ve silme çalışma (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) açısından kayıt kümesinin bu işlevlerin eylemleri açıklar.  
  
[Kayıt kümesi: Daha fazla ilgili güncelleştirmeleri (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md) kayıt güncelleştirme hikayesi yaptığınız güncelleştirmeler diğer güncelleştirmeleri ile nasıl etkileşime işlemlerin güncelleştirmeleri etkilemesi ve güncelleştirme işlemleri sürüyor kayıt kapatma veya kaydırma nasıl etkilediğini açıklayarak tamamlar. Kullanıcılar.  
  
##  <a name="_core_your_role_in_recordset_updating"></a> Kayıt kümesi güncelleştiriliyor sizin rolünüz  

Aşağıdaki tablo, eklemek, düzenlemek veya framework sizin için ne yaptığını birlikte kayıtları silmek için kayıt kümeleri kullanarak rolünüz gösterir.  
  
### <a name="recordset-updating-you-and-the-framework"></a>Kayıt kümesi güncelleştiriliyor: Siz ve Framework  
  
|Bunun için,|Framework|  
|---------|-------------------|  
|Veri kaynağı güncellenebilir (veya eklenebilir) olup olmadığını belirler.|Kaynakları [CDatabase](../../mfc/reference/cdatabase-class.md) üye işlevleri veri kaynağının güncellenebilirliği veya eklenebilirliğini denetlemek için.|  
|Güncelleştirilebilir bir kayıt kümesi (herhangi bir türde) açın.||  
|Çağırarak kayıt güncelleştirilebilir olup olmadığını `CRecordset` işlevleri gibi güncelleştirme `CanUpdate` veya `CanAppend`.||  
|Kayıt kümesi ekleme, düzenleme ve kayıtları silmek için üye işlevlerini çağırın.|Veri kaynağı, kayıt kümesi nesnesi arasındaki veri değişimi mekanizması yönetir.|  
|Güncelleştirme işlemini denetlemek için isteğe bağlı olarak işlem kullanın.|Kaynakları `CDatabase` işlemleri desteklemek için üye işlevleri.|  
  
İşlemler hakkında daha fazla bilgi için bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_the_edit_buffer"></a> Düzenleme ara  

Topluca alındığında, bir kayıt kümesi alan veri üyeleri bir kayıt içeren bir düzen arabellek olarak hizmet — geçerli kayıt. Güncelleştirme işlemleri bu arabelleği geçerli kayıt üzerinde çalışmak için kullanın.  
  
- Bir kayıt eklemek, düzenleme arabelleği yeni bir kayıt oluşturmak için kullanılır. Kayıt eklemeyi bitirdikten sonra daha önce geçerli kayıt yeniden geçerli olur.  
  
- Güncelleştirdiğinizde, bağlantı (edit) bir kaydı düzenleme arabellek alan veri üyeleri kayıt kümesinin yeni değerlere ayarlamak için kullanılır. Güncelleştirme işiniz bittiğinde, güncelleştirilen kaydı hala geçerli olur.  
  
Çağırdığınızda [AddNew](../../mfc/reference/crecordset-class.md#addnew) veya [Düzenle](../../mfc/reference/crecordset-class.md#edit), daha sonra gerektiğinde geri yüklenebilmesi için geçerli kayıt depolanır. Çağırdığınızda [Sil](../../mfc/reference/crecordset-class.md#delete), geçerli kayıt depolanmaz, ancak silindi olarak işaretlendi ve başka bir kayıtla kaydırma gerekir.  
  
> [!NOTE]
>  Düzenleme arabellek kayıt silmeyi herhangi bir rol oynar. Geçerli kayıt sildiğinizde, kaydı silinmiş olarak işaretlenmiş ve başka bir kayıda kaydırma kadar kayıt "kaydında değil" olur.  
  
##  <a name="_core_dynasets_and_snapshots"></a> Dinamik kümeler ve anlık görüntüleri  

[Dynaset'ler](../../data/odbc/dynaset.md) kayda gezinirken bir kaydın içeriğini yenileyin. [Anlık görüntüleri](../../data/odbc/snapshot.md) kayıtları statik temsillerini olduğundan, çağırmadığınız sürece bir kaydın içeriğini yenilenmedi [Requery](../../mfc/reference/crecordset-class.md#requery). Dynaset'ler tüm işlevlerini kullanmak için doğru düzeyini ODBC API desteği için uygun bir ODBC sürücüsü ile çalışmalısınız. Daha fazla bilgi için [ODBC](../../data/odbc/odbc-basics.md) ve [Dynaset](../../data/odbc/dynaset.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: AddNew, Düzenleme ve Silmenin Çalışması (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)