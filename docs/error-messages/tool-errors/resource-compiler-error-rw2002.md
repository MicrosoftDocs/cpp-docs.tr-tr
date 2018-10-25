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
ms.openlocfilehash: b90a0800708af41037325204a00c808bec2a7d20
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080864"
---
# <a name="resource-compiler-error-rw2002"></a>Kaynak Derleyicisi Hatası RW2002

Ayrıştırma hatası

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. **Hızlandırıcı türü (ASCII veya VIRTKEY'e) gerekli**

   `type` Alanındaki **HIZLANDIRICILARI** deyimi ASCII veya VIRTKEY'e değer içermesi gerekir.

1. **Hızlandırıcı tablosunu beklenen BEGIN**

   **Başlamak** anahtar sözcüğü hemen izlemelidir **HIZLANDIRICILARI** anahtar sözcüğü.

1. **İletişim kutusunda beklenen BEGIN**

   **Başlamak** anahtar sözcüğü hemen izlemelidir **iletişim** anahtar sözcüğü.

1. **Başlangıç menüsünde bekleniyor**

   **Başlamak** anahtar sözcüğü hemen izlemelidir **menü** anahtar sözcüğü.

1. **RCData içinde beklenen BEGIN**

   **Başlamak** anahtar sözcüğü hemen izlemelidir **RCDATA** anahtar sözcüğü.

1. **Dize tablosunda beklenen BEGIN anahtar sözcüğü**

   **Başlamak** anahtar sözcüğü hemen izlemelidir **STRINGTABLE** anahtar sözcüğü.

1. **Dize sabitleri yeniden kullanamazsınız**

   İki kez içinde aynı değere kullanmakta olduğunuz bir **STRINGTABLE** deyimi. Ondalık ve onaltılık değerlerini çakışan karıştırma değil emin olun. Her kimliği bir **STRINGTABLE** benzersiz olması gerekir. En yüksek düzey verimlilik için 16 bir Çoklu Başlangıç bitişik sabitleri kullanın.

1. **Denetim karakteri je mimo rozsah [^ A - ^ Z]**

   Bir denetim karakteri **HIZLANDIRICILARI** deyimi geçerli değil. Giriş işaretini aşağıdaki karakter (**^**) arasında olmalıdır A-Z, kapsamlı.

9. **Boş Menü izin verilmiyor**

   Bir **son** anahtar sözcüğü görünür menü öğeleri tanımlanan önce **menü** deyimi. Kaynak Derleyicisi boş menüleri izin vermez. Tüm açık tırnak içine sahip olmadığınız emin **menü** deyimi.

10. **Son iletişim kutusunda bekleniyor**

   **Son** anahtar sözcüğü, sonunda gerçekleşmelidir bir **iletişim** deyimi. Önceki deyimin sol hiçbir açık tırnak işareti olmadığından emin olun.

11. **Son menüde bekleniyor**

   **Son** anahtar sözcüğü, sonunda gelmelidir bir **menü** deyimi. Sahip olmadığınız açık tüm tırnak işaretlerini veya eşleşmeyen bir çift emin **başlamak** ve **son** deyimleri.

12. **Hızlandırıcı tablo beklenen virgülle**

   Kaynak Derleyicisi arasına virgül gerektirir `event` ve *idvalue* alanlarını **HIZLANDIRICILARI** deyimi.

13. **Beklenen denetim sınıfı adı**

   `class` Alanını bir **denetimi** deyiminde **iletişim** deyimi aşağıdaki türlerden biri olmalıdır: DÜĞME, COMBOBOX, düzenleme, liste kutusu, kaydırma çubuğu, statik veya kullanıcı tanımlı. Sınıf doğru yazıldığından emin olun.

14. **Yazı tipi adını bekleniyor**

   *Yazı tipi* yazı tipi seçeneğinin alan **iletişim** deyimi, çift tırnak işareti içine alınmış bir ASCII karakter dizesi olmalıdır. Bu alan bir yazı tipinin adını belirtir.

15. **MenuItem için beklenen kimlik değeri**

   **Menü** deyimi içermelidir bir *menuID* alanı adı ya da menü kaynağı tanımlayan numara belirtir.

16. **Menü beklenen dize**

   Her **MENUITEM** ve **açılan** deyimi içermelidir bir *metin* çift tırnak işareti menü öğesi ya da açılan adını belirten dize alanı menüsü. A **MENUITEM AYIRICI** alıntılanmış dize ifadesi gerektirir.

17. **komut sayısal değer bekleniyor**

   Kaynak derleyicisi bir sayısal bekliyordu *idvalue* alanındaki **HIZLANDIRICILARI** deyimi. Kullandığınız emin bir `#define` sabit değeri belirtin ve sabiti doğru yazıldığından.

18. **Sayısal sabit dize tablosunda bekleniyor**

   Bir sayısal sabit tanımlanmış bir `#define` deyimi, hemen izlemelidir **başlamak** anahtar sözcüğü bir **STRINGTABLE** deyimi.

19. **Sayısal punto boyutu bekleniyor**

   *Pointsize* yazı tipi seçeneğinin alan **iletişim** deyimi, bir tamsayı noktası boyut değeri olmalıdır.

20. **Sayısal iletişim sabiti bekleniyordu**

   A **iletişim** çalıştın için tamsayı değerleri *x, y, genişlik*, ve *yükseklik* alanları. Bu değerlerden sonra yer aldığından emin olun **iletişim** anahtar sözcüğü ve negatif olduklarını değil.

21. **STRINGTABLE beklenen dize**

   Bir dizeyi her birinden sonra beklenen *stringıd* değerini bir **STRINGTABLE** deyimi.

22. **Beklenen dize veya sabit Hızlandırıcı komutu**

   Kaynak Derleyicisi ne tür bir anahtar Hızlandırıcı için ayarlanan belirlemek mümkün değildi. `event` Alanındaki **HIZLANDIRICILARI** ifade geçersiz olabilir.

23. **KODU için sayı bekleniyor**

   Bir sayı bekleniyor `id` alan bir denetim deyiminin **iletişim** deyimi. Bir sayı olduğundan emin olun veya `#define` denetim kimliğini for deyimi

24. **İletişim kutusu sınıfında alıntılanmış dize bekleniyor**

   `class` Alan sınıfı seçeneğinin **iletişim** deyimi, bir tamsayı ya da çift tırnak işareti içine alınmış bir dize olmalıdır.

25. **İletişim başlığı alıntılanmış dize bekleniyor**

   `captiontext` Açıklamalı alt yazı seçeneğinin alan **iletişim** deyimi, çift tırnak işareti içine alınmış bir ASCII karakter dizesi olmalıdır.

26. **Soubor nebyl nalezen: dosya adı**

   Kaynak derleyici komut satırında belirtilen dosya bulunamadı. Dosya başka bir dizine taşınmış olan ve dosya adı veya yolu olup doğru yazıldığından olmadığını kontrol edin. Dosyaları kullanmak için aranır **INCLUDE** ortam değişkeni veya varsa Workbench Visual ayarı.

27. **Yazı tipi adları sıra sayıları olmalıdır**

   *Pointsize* yazı tipi ifade alanında bir dize değil bir tamsayı olmalıdır.

28. **Geçersiz Hızlandırıcı**

   Bir `event` alanındaki **HIZLANDIRICILARI** deyimi tanınmadı veya ikiden fazla karakter uzunluğunda olan.

29. **Geçersiz Hızlandırıcı türü (ASCII veya VIRTKEY'e)**

   `type` Alanındaki **HIZLANDIRICILARI** deyimi ASCII veya VIRTKEY'e değer içermesi gerekir.

30. **Geçersiz denetim karakteri**

   Bir denetim karakteri **HIZLANDIRICILARI** deyimi geçerli değil. Geçerli bir denetim karakteri bir şapka (^) (yalnızca) izleyen bir harfi oluşur.

31. **Geçersiz denetim türü**

   Her denetim deyiminde bir **iletişim** deyimi aşağıdakilerden biri olmalıdır: onay kutusunu, COMBOBOX, denetimi, CTEXT, DEFPUSHBUTTON, EDITTEXT, GROUPBOX, SİMGE, liste kutusu, LTEXT, basma düğmesi, RADIOBUTTON, RTEXT, kaydırma çubuğu. Bu denetim ifadeleri doğru yazıldığından emin olun.

32. **Geçersiz tür**

   Kaynak türü WINDOWS.h dosyasında tanımlı türleri arasında değildi.

33. **Metin dizesi veya sıra denetiminde bekleniyor**

   *Metin* alanını bir **denetimi** deyiminde **iletişim** deyimi, bir metin dizesi veya denetim türü için sıralı bir başvuru olmalıdır. Bir sıra kullanan yaparsanız emin, sahip olduğunuz bir `#define` denetim ifadesi.

34. **Eşleşmeyen parantezler**

   Kapattığınız her açık parantez olduğundan emin olun **iletişim** deyimi.

35. **RCData beklenmeyen değer**

   *Ham verileri* değerler **RCDATA** deyimi bir tamsayı veya dize olmalıdır, her bir virgülle ayrılmış. Değil virgül bırakın veya bir dize etrafında tırnak işareti kullanıma bırakın emin olun.

36. **Bilinmeyen menü alt tür**

   *Öğesi tanımını* alanını **menü** deyimi yalnızca içerebilir **MENUITEM** ve **açılan** deyimleri.