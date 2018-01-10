---
title: "Yapı UNWIND_CODE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 104955d8-7e33-4c5a-b0c6-3254648f0af3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76059ff24b46fd537db0c2670a30cf3f42ee2166
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="struct-unwindcode"></a>struct UNWIND_CODE
Geriye doğru izleme kod dizisi RSP ve kalıcı Yazmaçları etkileyen giriş bölümünde işlemleri dizisini kaydetmek için kullanılır. Her kod öğesi aşağıdaki biçime sahiptir:  
  
|||  
|-|-|  
|UBYTE|Başlangıç bölümündeki mesafe|  
|UBYTE: 4|Bırakma işlemi kodu|  
|UBYTE: 4|İşlem bilgisi|  
  
 Dizi giriş uzaklığı azalan göre sıralanır.  
  
 **Başlangıç bölümündeki mesafe**  
 Bu işlem, artı 1 (diğer bir deyişle, sonraki yönerge başlangıç uzaklığı) gerçekleştirir yönerge ucunun giriş başından uzaklık.  
  
 **Bırakma işlemi kodu**  
 Not: Bir değer yerel yığın çerçevesinde imzasız bir uzaklık belirli işlemi kodları gerektirir. Sabit yığın ayırma başlangıcı (en düşük adres) başlangıç uzaklığı. UNWIND_INFO çerçeve kaydı alanında sıfır olursa bu uzaklık RSP dayalıdır. Çerçeve yazmaç alanı sıfır değilse, bu FP reg oluşturulduğunda RSP bulunduğu gelen uzaklığı. Bu FP reg eksi FP reg sapmasına eşittir (16 * ölçeklendirilmiş çerçeve kaydı uzaklığı UNWIND_INFO). Ardından FP reg kullanılırsa, FP reg giriş kurulduktan sonra uzaklığı alma bırakma kod yalnızca kullanılmalıdır.  
  
 UWOP_SAVE_XMM128 ve UWOP_SAVE_XMM128_FAR hariç tüm işlem kodları için uzaklık ilgi tüm yığın değerleri 8 baytlık sınırları (her zaman yığını 16 bayt hizalı'dır) depolandığından 8, birden fazla her zaman olacaktır. Kısa bir uzaklık (değerinden 512 K) alır işlemi kodları için bu kod için düğümlerdeki son USHORT 8'e bölünen uzaklığı tutar. Uzun bir uzaklık alır işlemi kodları (512K < = < 4 GB uzaklığı), bu kod için son iki USHORT düğümleri uzaklık (little endian biçiminde) tutun.  
  
 Tüm 128-bit XMM işlemleri 16 bayt hizalı bellekte gerçekleşmesi gerektiği UWOP_SAVE_XMM128 ve UWOP_SAVE_XMM128_FAR işlem için uzaklık daima 16, birden fazla olur. Bu nedenle, 16 ölçek faktörü 1 M değerinden az uzaklıklarını sorgulamasına UWOP_SAVE_XMM128 için kullanılır.  
  
 Bırakma işlemi şunlardan birini koddur:  
  
 UWOP_PUSH_NONVOL (0) 1 düğümü  
  
 Kalıcı tamsayı kaydını, azaltma RSP 8 tarafından iletin. İşlem bilgisi kayıt sayısıdır. Sonuç kısıtlamalar nedeniyle, UWOP_PUSH_NONVOL bırakma kodlarının gerekir öncelikle giriş bölümünde görünür ve buna bağlı olarak, geriye doğru izleme kodu dizisinde son, unutmayın. Bu göreli sıralama UWOP_PUSH_MACHFRAME dışındaki diğer tüm bırakma kodları uygular.  
  
 UWOP_ALLOC_LARGE (1) 2 veya 3 düğümleri  
  
 Yığın üzerinde büyük ölçekli bir alan ayırın. İki tür vardır. İşlem bilgisi 0 sonra bölü ayırma boyutu eşitse 8 512 K - 8 kadar bir ayırma izin vererek sonraki yuvaya kaydedilir. İşlem bilgisi eşittir 1 sonra ayırma ölçeklendirilmemiş boyutunu ayırmaya olanak vererek little endian biçiminde sonraki iki yuvaya kaydedilir en fazla 4GB - 8.  
  
 UWOP_ALLOC_SMALL (2) 1 düğümü  
  
 Yığın üzerinde küçük ölçekli bir alan ayırın. Bilgi alanı ayırma boyutu işlemidir * 8 + 8, 8 ayırma 128 bayt izin verme.  
  
 Yığın ayırma için bırakma kodu, her zaman en kısa olası kodlamayı kullanmanız gerekir:  
  
|||  
|-|-|  
|**Ayırma boyutu**|**Bırakma kodu**|  
|8 ile 128 bayt|UWOP_ALLOC_SMALL|  
|136 ile 512K - 8 bayt|UWOP_ALLOC_LARGE, işlem bilgisi = 0|  
|512K ile 4G - 8 bayt|UWOP_ALLOC_LARGE, işlem bilgisi = 1|  
  
 UWOP_SET_FPREG (3) 1 düğümü  
  
 Bazı geçerli RSP uzaklık kaydı ayarlayarak çerçeve işaretçisi kaydı oluşturun. Uzaklık UNWIND_INFO çerçeve kaydı uzaklığı (ölçekli) alanına eşittir * 16, 0'dan uzaklıkları 240 izin verme. Bir uzaklık kullanımına kısa yönerge formları kullanmak daha fazla erişim vererek kod yoğunluğu yardımcı sabit yığın ayırma ortasını işaret eden bir çerçeve işaretçisi oluşturmayı izin verir. İşlem bilgisi alanının ayrılmıştır ve kullanılmamalıdır unutmayın.  
  
 UWOP_SAVE_NONVOL (4) 2 düğümleri  
  
 PUSH yerine MOV kullanarak Yığında kalıcı tamsayı kaydını kaydedin. Bu öncelikle sabit için bir kayıt önceden ayrılmış bir konuma yığına kaydedildiği kullanılır. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmiş tarafından-8 yığın uzaklık sonraki kaydedilen işlem kodu yuva, yukarıdaki notta açıklandığı gibi bırakma.  
  
 UWOP_SAVE_NONVOL_FAR (5) 3 düğümleri  
  
 Kalıcı tamsayı kaydını yığın MOV yerine PUSH kullanarak mesafesi ile kaydedin. Bu öncelikle sabit için bir kayıt önceden ayrılmış bir konuma yığına kaydedildiği kullanılır. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmemiş yığın sapması sonraki kaydedilir iki yukarıdaki notta açıklandığı gibi işlem kod yuvalarında bırakma.  
  
 UWOP_SAVE_XMM128 (8) 2 düğümleri  
  
 XMM kaydının tüm 128 bit yığında kaydedin. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmiş tarafından-16 yığın uzaklık sonraki yuvaya kaydedilir.  
  
 UWOP_SAVE_XMM128_FAR (9) 3 düğümleri  
  
 XMM kaydının tüm 128 bit yığın mesafesi ile kaydedin. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmemiş yığın sapması sonraki iki yuvalarında kaydedilir.  
  
 UWOP_PUSH_MACHFRAME (10) 1 düğümü  
  
 Makine çatısını gönderin.  Bu, bir donanım kesme ya da özel durum etkisini kaydetmek için kullanılır. İki tür vardır. İşlem bilgisi 0 eşitse, aşağıdaki yığına:  
  
|||  
|-|-|  
|RSP + 32|SS|  
|RSP + 24|Eski RSP|  
|RSP + 16|EFLAGS|  
|RSP + 8|CS|  
|RSP|KOPYALAMA|  
  
 Aşağıdaki yerine gönderilen sonra işlem bilgisi 1, eşitse:  
  
|||  
|-|-|  
|RSP + 40|SS|  
|RSP + 32|Eski RSP|  
|RSP + 24|EFLAGS|  
|RSP + 16|CS|  
|RSP + 8|KOPYALAMA|  
|RSP|Hata kodu|  
  
 Bu bırakma kodu her zaman hangi asla gerçekleştirilmeden ancak bunun yerine önce bir kesme yordamının gerçek giriş noktası görüntülenir ve yalnızca bir makine çerçevesi itme benzetimini yapmak için bir yer sağlamak için mevcut bir kukla giriş bölümünde görüntülenir. UWOP_PUSH_MACHFRAME makinenin kavramsal olarak aşağıdaki yapmıştır gösteren benzetimi kaydeder:  
  
 RIP dönüş adresi yığına yukarıdan pop *Temp*  
  
 SS Gönder  
  
 Eski RSP bildirme  
  
 EFLAGS Gönder  
  
 Anında iletme CS  
  
 Anında iletme *Temp*  
  
 (Op bilgisi 1 değerine eşitse) hata kodunu bildirme  
  
 40 tarafından Benzetilen UWOP_PUSH_MACHFRAME işlemi azaltır RSP (op bilgisi 0 değerine eşittir) veya 48 (op bilgisi eşittir 1).  
  
 **İşlem bilgisi**  
 Bu 4 bitin anlamı işlem koduna bağlıdır. Genel amaçlı (tamsayı) kaydı kodlamak için aşağıdaki eşleme kullanılır:  
  
|||  
|-|-|  
|0|RAX|  
|1.|RCX|  
|2|RDX|  
|3|RBX|  
|4|RSP|  
|5|RBP|  
|6|RSI|  
|7|RDI|  
|8-15|R8 R15 kayıtları için|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme için Veri Bırakma, Hata Ayıklayıcı Desteği](../build/unwind-data-for-exception-handling-debugger-support.md)