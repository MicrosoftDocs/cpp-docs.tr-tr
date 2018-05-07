---
title: Kaynak Derleyicisi hatası RW2002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW2002
dev_langs:
- C++
helpviewer_keywords:
- RW2002
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb42298a7140439e3578281de60075f540b09175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-error-rw2002"></a>Kaynak Derleyicisi Hatası RW2002
Ayrıştırma hatası  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  **Hızlandırıcı türü (ASCII veya VIRTKEY) gerekli**  
  
     `type` Alanındaki **HIZLANDIRICILARI** deyimi ASCII veya VIRTKEY değer içermesi gerekir.  
  
2.  **Hızlandırıcı tablosunu beklenen BAŞLAMA**  
  
     **Başlamak** anahtar sözcüğü hemen uymalıdır **HIZLANDIRICILARI** anahtar sözcüğü.  
  
3.  **İletişim kutusunda beklenen BAŞLAMA**  
  
     **Başlamak** anahtar sözcüğü hemen uymalıdır **iletişim** anahtar sözcüğü.  
  
4.  **Başlangıç menüsünde bekleniyor**  
  
     **Başlamak** anahtar sözcüğü hemen uymalıdır **menü** anahtar sözcüğü.  
  
5.  **RCData içinde beklenen BAŞLAMA**  
  
     **Başlamak** anahtar sözcüğü hemen uymalıdır **RCDATA** anahtar sözcüğü.  
  
6.  **Dize tabloda beklenen başlangıç anahtar sözcüğü**  
  
     **Başlamak** anahtar sözcüğü hemen uymalıdır **STRINGTABLE** anahtar sözcüğü.  
  
7.  **dize sabitleri yeniden kullanamazsınız**  
  
     İki kez içinde aynı değere kullanarak bir **STRINGTABLE** deyimi. Ondalık ve onaltılık değerler çakışan karıştırma değil emin olun. Her Kimliğinde bir **STRINGTABLE** benzersiz olması gerekir. En yüksek verimlilik için 16 birden fazla üzerinde Başlat bitişik sabitleri kullanın.  
  
8.  **Denetim karakteri aralık dışında [^ A - ^ Z]**  
  
     Bir denetim karakteri **HIZLANDIRICILARI** ifadesi geçersiz. Aşağıdaki düzeltme işareti karakteri (**^**) arasında olmalıdır A ile Z, kapsayıcı.  
  
9. **izin boş menüleri**  
  
     Bir **son** anahtar sözcüğü görünür tüm menü öğelerini tanımlanan önce **menü** deyimi. Kaynak Derleyicisi boş menüleri izin vermez. Tüm açık tırnak içine sahip olmadığınız emin olun **menü** deyimi.  
  
10. **Son iletişim kutusunda bekleniyor**  
  
     **Son** anahtar sözcüğü sonunda gerçekleşmesi gereken bir **iletişim** deyimi. Önceki deyimden sol hiçbir açık tırnak işareti olmadığından emin olun.  
  
11. **Menüde beklenen bitiş**  
  
     **Son** anahtar sözcüğü sonunda olması gereken bir **menü** deyimi. Değil tüm açık tırnak işaretlerini veya eşleşmeyen bir çifti olduğundan emin olun **başlamak** ve **son** deyimleri.  
  
12. **Hızlandırıcı tablo beklenen virgülle**  
  
     Kaynak Derleyicisi arasında virgül gerektirir `event` ve *idvalue* alanlarını **HIZLANDIRICILARI** deyimi.  
  
13. **Beklenen denetim sınıf adı**  
  
     `class` Alanını bir **denetim** deyiminde **iletişim** deyimi aşağıdaki türlerden biri olmalıdır: DÜĞME, COMBOBOX, düzenleme, LISTBOX, kaydırma çubuğu, statik veya kullanıcı tanımlı. Sınıf doğru yazıldığından emin olun.  
  
14. **Yazı tipi adını bekleniyor**  
  
     *Yazı tipi* yazı tipi seçeneğinde alanını **iletişim** deyimi çift tırnak işaretleri içine bir ASCII karakter dizesi olması gerekir. Bu alan bir yazı tipi adını belirtir.  
  
15. **MenuItem beklenen kimliği değeri**  
  
     **Menü** deyimi içermelidir bir *menuID* alanın adını veya menü kaynağı tanımlayan numarasını belirtir.  
  
16. **Beklenen menü dize**  
  
     Her **MENUITEM** ve **açılan** deyimi içermelidir bir *metin* çift tırnak işaretleri içine menü öğesi veya açılır pencere adını belirten dize alanı menüsü. A **MENUITEM AYIRICI** deyimi tırnak içine alınmış dize gerektirir.  
  
17. **Sayısal komut değeri bekleniyordu**  
  
     Kaynak Derleyicisi sayısal bekleniyor *idvalue* alanındaki **HIZLANDIRICILARI** deyimi. Kullandığınız olduğundan emin olun bir `#define` sabit değeri belirtin ve sabit doğru yazıldığından.  
  
18. **Dize tablodaki sayısal sabit bekleniyor**  
  
     Sayısal sabit tanımlanan bir `#define` deyimi, hemen uymalıdır **başlamak** in anahtar sözcüğü bir **STRINGTABLE** deyimi.  
  
19. **Sayısal punto boyutunu bekleniyor**  
  
     *Pointsize* yazı tipi seçeneğinde alanını **iletişim** deyimi bir nokta boyutu tamsayı olmalıdır.  
  
20. **beklenen sayısal iletişim sabiti**  
  
     A **iletişim** deyimi için tamsayı değerlerini gerektirir *x, y, genişlik*, ve *yükseklik* alanları. Bu değerleri sonra dahil olduğundan emin olun **iletişim** anahtar sözcüğü ve negatif olmalarını değil.  
  
21. **STRINGTABLE beklenen dizesinde**  
  
     Her komuttan sonra bir dize bekleniyor *DizeNo'nun* değeri bir **STRINGTABLE** deyimi.  
  
22. **Beklenen dizeyi veya sabit Hızlandırıcı komutu**  
  
     Kaynak Derleyicisi ne tür bir anahtar için Hızlandırıcı ayarlanıyor belirlemek mümkün değildi. `event` Alanındaki **HIZLANDIRICILARI** ifade geçersiz olabilir.  
  
23. **Kimliği için sayı bekleniyor**  
  
     İçin bir sayı bekleniyor `id` denetim deyiminde alanını **iletişim** deyimi. Bir sayı olduğundan emin olun veya `#define` denetim kimliği için deyimi  
  
24. **İletişim kutusu sınıfında tırnak içine alınmış dize bekleniyor**  
  
     `class` Sınıfı seçeneğinde alanını **iletişim** deyimi bir tamsayı ya da çift tırnak içine alınmış bir dize olmalıdır.  
  
25. **İletişim kutusu başlığı tırnak içine alınmış dize bekleniyor**  
  
     `captiontext` Resim yazısı seçeneğinde alanını **iletişim** deyimi çift tırnak işaretleri içine bir ASCII karakter dizesi olması gerekir.  
  
26. **Dosya bulunamadı: dosya adı**  
  
     Kaynak Derleyicisi komut satırında belirtilen dosya bulunamadı. Dosya başka bir dizine taşınmış olan ve dosya adı veya yolu olup doğru yazıldığından denetleyin. Dosyaları kullanmak için aranır **INCLUDE** ortam değişkeni veya Visual çalışma ekranı ayarı, varsa.  
  
27. **Yazı tipi adlarını sıra numaraları olmalıdır**  
  
     *Pointsize* yazı tipi deyimi alanında, bir dizeyi bir tamsayı olmalıdır.  
  
28. **Geçersiz hızlandırma**  
  
     Bir `event` alanındaki **HIZLANDIRICILARI** deyimi tanınmadı ya da birden fazla iki karakter uzunluğunda.  
  
29. **Geçersiz Hızlandırıcı türü (ASCII veya VIRTKEY)**  
  
     `type` Alanındaki **HIZLANDIRICILARI** deyimi ASCII veya VIRTKEY değer içermesi gerekir.  
  
30. **Geçersiz denetim karakteri**  
  
     Bir denetim karakteri **HIZLANDIRICILARI** ifadesi geçersiz. Geçerli bir denetim karakteri bir harf (yalnızca) şapka (^) aşağıdaki oluşur.  
  
31. **Geçersiz denetim türü**  
  
     Her denetim deyiminde bir **iletişim** deyimi şunlardan biri olmalıdır: onay kutusu, COMBOBOX, Denetim, CTEXT, DEFPUSHBUTTON, EDITTEXT, GROUPBOX, SİMGE, LISTBOX, LTEXT, basma düğmesi, RADIOBUTTON, RTEXT, kaydırma çubuğu. Bu denetim ifadeleri doğru yazıldığından emin olun.  
  
32. **Geçersiz tür**  
  
     Kaynak türü WINDOWS.h dosyasında tanımlanan türleri arasında değil.  
  
33. **Metin dizesi veya denetiminde beklenen sıra**  
  
     *Metin* alanını bir **denetim** deyiminde **iletişim** deyimi bir metin dizesi veya denetim türü için sıralı bir başvurusu olmalıdır. Bir sıra kullanarak yaparsanız emin, sahip olduğunuz bir `#define` denetimi bildirimi.  
  
34. **Eşleşmeyen ayraçları**  
  
     Kapattığınız her açık parantez olduğundan emin olun **iletişim** deyimi.  
  
35. **RCData beklenmeyen değer**  
  
     *Ham verileri* değerler **RCDATA** , her virgülle ayrılmış tamsayı veya dize deyimi olmalıdır. Değil virgül bırakın veya bir dize etrafında tırnak işareti çıkışı bırakın emin olun.  
  
36. **Bilinmeyen menü alt türü**  
  
     *Öğesi tanımı* alanını **menü** deyimi yalnızca içerebilir **MENUITEM** ve **açılan** deyimleri.