---
title: Microsoft Macro Assembler BNF dilbilgisi
description: X için MASG 'nin BNF açıklaması.
ms.date: 12/17/2019
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), BNF reference
ms.openlocfilehash: 1a9577292e60db73838e5e6b850a4634db959fd6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075459"
---
# <a name="microsoft-macro-assembler-bnf-grammar"></a>Microsoft Macro Assembler BNF dilbilgisi

Bu sayfa masa dilbilgisinin BNF açıklamasını içerir. Başvuru konularına bir ek olarak sağlanır ve tamamlanmayacakları garanti edilmez. Anahtar sözcükler, parametreler, işlemler vb. hakkında tam bilgi için lütfen başvuru konularına bakın.

BNF kullanımını göstermek için aşağıdaki diyagramda, nonterminalsiz *Typedefdir*Ile başlayarak typedef yönergesinin tanımı gösterilmektedir.

![MASMG BNF örneği](media/bnf.png)

Her yatay küme ayracın altındaki girdiler ( **NEAR16**, **NEAR32**, **FAR16**ve **FAR32**gibi) veya daha fazla tanımlanabilir terminallerdir ( *niteleyici*, *qualifiedtype*, *Distance*ve *protospec*gibi). *Typedefdir* tanımındaki her bir italik olmayan Terminal, BNF içindeki bir giriştir. Üç dikey nokta, kolaylık sağlaması için, bu şekilde basit olmayan, terminalin bir dal tanımını gösterir.

BNF dilbilgisi özyinelemeli tanımlara izin verir. Örneğin, dilbilgisi, qualifiedtype için olası bir tanım olarak qualifiedType kullanır, bu da niteleyici tanımının bir bileşenidir. "|" Sembolü, örneğin *EndOfLine* | *yorumu*gibi alternatif ifadeler arasında seçim belirtir. Çift küme ayraçları isteğe bağlı bir parametre belirtir, örneğin ⟦ *Macroparmlist* ⟧. Köşeli ayraçlar aslında kaynak kodunda görünmez.

## <a name="masm-nonterminals"></a>MASMNONTERMINALLERI

*;;* \
&nbsp;&nbsp;&nbsp;&nbsp;*EndOfLine* | *Açıklama*

*= Dir*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği* = *immExpr* ;;

*ADDOP*\
&nbsp;&nbsp;&nbsp;&nbsp;+ | -

*Aexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*terimi* | *aexpr* && *terimi*

*Altıd*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*aracı*\
&nbsp;&nbsp;&nbsp;&nbsp;*charlist*

*Asminstruction*\
&nbsp;&nbsp;&nbsp;&nbsp;*Anımsatıcı* ⟦ *exprList* ⟧

*assumeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;**varsay** ; *assumeList*
&nbsp;&nbsp;&nbsp;| &nbsp;**HIÇBIR şey varsay** ;;

*assumeList*\
&nbsp;&nbsp;&nbsp;&nbsp;*Assumeregister* | *assumeList* , *assumeregister*\

*Assumereg*\
&nbsp;&nbsp;&nbsp;&nbsp;*kayıt* : *assumeVal*

*Assumeregister*\
&nbsp;&nbsp;&nbsp;&nbsp;*assumeSegReg* | *Assumereg*

*assumeSegReg*\
&nbsp;&nbsp;&nbsp;&nbsp;*segmentRegister* : *assumeSegVal*

*assumeSegVal*\
&nbsp;&nbsp;&nbsp;&nbsp;*Frameexpr* | **nothıng** | **hata**

*assumeVal*\
&nbsp;&nbsp;&nbsp;&nbsp;*Qualifiedtype* | **nothıng** | **hata**

*bcdConst*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *işareti* ⟧ *decnumber*

*BinaryOp*\
&nbsp;&nbsp;&nbsp;&nbsp;= = |! = | > = | < = | > | < | &

*Bitdef*\
&nbsp;&nbsp;&nbsp;&nbsp;*Bitfieldıd* : *bitfieldsize* ⟦ = *constExpr* ⟧

*Bitdeflist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Bitdef* | *bitdeflist* , ⟦;; ⟧ *Bitdef*

*Bitfieldıd*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*Bitfieldsize*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*Blockdeyimlerini*\
&nbsp;&nbsp;&nbsp;&nbsp;*Directivelist*\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. DEVAM edın** **. IF** *cexpr* ⟧ \ ise
&nbsp;&nbsp;&nbsp;&nbsp;|  **. BREAK** ⟦ **. If** *cexpr* ⟧

*bool*\
&nbsp;&nbsp;&nbsp;&nbsp;**TRUE** | **false**

*Byteregister*\
&nbsp;&nbsp;&nbsp;&nbsp;AL | AH | CL | CH | DL | DH | BL | BH | R8B | R9B | R10B | R11B | R12B | R13B | R14B | R15B

*cexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*Aexpr* | *cexpr* || *aexpr*

*karakter*\
&nbsp;&nbsp;, satır besleme (10) dışında 0 – 255 aralığında sıra içeren herhangi bir karakter &nbsp;&nbsp;.

*charlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*karakteri* | *charlist* karakteri

*className*\
&nbsp;&nbsp;&nbsp;&nbsp;*dizesi*

*Commdecl*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *yaklaştığında* en çok ⟧ ⟦ *langtype* ⟧ *ID* : *CommType*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦: *constExpr* ⟧

*Commdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**COMM**\
&nbsp;&nbsp;&nbsp;&nbsp;*Commlist* ;;

*açıklama*\
&nbsp;&nbsp;&nbsp;&nbsp;; *metin* ;;

*Commentdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**Açıklama** *sınırlayıcısı*\
&nbsp;&nbsp;&nbsp;&nbsp;*metin*\
&nbsp;&nbsp;&nbsp;&nbsp;*metin* *sınırlayıcı* *metni* ;;

*Commlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*commdecl* | *commlist* , *commdecl*

*CommType*\
&nbsp;&nbsp;&nbsp;&nbsp;*türü* | *constExpr*

*sabit*\
&nbsp;&nbsp;&nbsp;&nbsp;*basamaklar* ⟦ *radixoverride* ⟧

*constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*Expr*

*Contextdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**PushContext** *contextıtemlist* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;**PopContext** *contextıtemlist* ;;

*ContextItem*\
&nbsp;&nbsp;&nbsp;&nbsp; **, | ** **CPU** ** | ** **listesini** | **varsayar** | 

*Contextıtemlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*contextıtem* | *contextıtemlist* , *ContextItem*

*Controlblock*\
&nbsp;&nbsp;&nbsp;&nbsp;*whileblock* | *repeatblock*

*Controldir*\
&nbsp;&nbsp;&nbsp;&nbsp;*controlIf* | *controlblock*

*Controtalseıf*\
&nbsp;&nbsp;&nbsp;&nbsp; **. &nbsp;&nbsp;** &nbsp;&nbsp;*cexpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*Directivelist* \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Controtalseıf* ⟧

*controlIf*\
&nbsp;&nbsp;&nbsp;&nbsp; **. &nbsp;&nbsp;** &nbsp;&nbsp;*cexpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*Directivelist*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Controtalseıf* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ **. ELSE** ;; \
&nbsp;&nbsp;&nbsp;&nbsp;[*Directivelist*⟧ \
&nbsp;&nbsp;&nbsp;&nbsp; **. ENDIF** ;;

*Eşişlemcisi*\
&nbsp;&nbsp;&nbsp;&nbsp;. 8087 |. 287 |. 387 |. NO87

*Crefdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Crefoption* ;;

*Crefoption*\
&nbsp;&nbsp;&nbsp;&nbsp; **. CREF**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. XCREF** ⟦ *ıdlist* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. NOCREF** ⟦ *ıdlist* ⟧

*Cxzexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr*\
&nbsp;&nbsp;&nbsp;&nbsp;|! *expr*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Expr* = = Expr \
&nbsp;&nbsp;&nbsp;&nbsp;| *Expr* ! = Expr

*Datadecl*\
&nbsp;&nbsp;&nbsp;&nbsp;DB | DW | DD | DF | DQ | DT | *dataType* | *TypeId*

*datadir*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *ID* ⟧ *DataItem* ;;

*dataıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;*Datadecl* *scalarinstlist*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Structtag* *structinstlist*\
&nbsp;&nbsp;&nbsp;&nbsp;| *TypeId* *structinstlist*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Uniontag* *structinstlist*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Recordtag* *recordinstlist*

*veri türü*\
&nbsp;&nbsp;&nbsp;&nbsp;bayt | SBYTE | SÖZCÜK | SWORD | DWORD | SDWORD | FWORD | QWORD | SQWORD | TBYTE | OKELIME | REAL4 | REAL8 | REAL10 | MMWORD | XMMWORD | YıLKELIME

*decdigit*\
&nbsp;&nbsp;&nbsp;&nbsp;0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | tuşlarına

*yaprak sayısı*\
&nbsp;&nbsp;&nbsp;&nbsp;*decdigit*\
&nbsp;&nbsp;&nbsp;&nbsp;| *yaprak* *döken* sayı

*sınırlayıcı*\
&nbsp;&nbsp;&nbsp;*boşluk karakteri* hariç tüm karakterleri &nbsp;

*basamaklar*\
&nbsp;&nbsp;&nbsp;&nbsp;*decdigit*\
&nbsp;&nbsp;&nbsp;&nbsp;| *basamak* *sayısı*\
&nbsp;&nbsp;&nbsp;&nbsp;| *basamak* onaltılık

*yönerge*\
&nbsp;&nbsp;&nbsp;&nbsp;*generaldir* | *segmentDef*

*Directivelist*\
&nbsp;&nbsp;&nbsp;&nbsp;*yönergesi* | *directivelist* *yönergesi*

*uzaklık*\
&nbsp;&nbsp;&nbsp;&nbsp;*yaklaştığında* en | **NEAR16** | **NEAR32** | **FAR16** | **FAR32**

*e01*\
&nbsp;&nbsp;&nbsp;&nbsp;E01 *Orop* *E02* | *E02*

*e02*\
&nbsp;&nbsp;&nbsp;&nbsp;E02 **ve** *E03* | *E03*

*e03*\
&nbsp;&nbsp;&nbsp;&nbsp;**Not** *E04* | *E04*

*e04*\
&nbsp;&nbsp;&nbsp;&nbsp;*E04* *RelOp* *E05* | *E05*

*e05*\
&nbsp;&nbsp;&nbsp;&nbsp;*E05* *ADDOP* *E06* | *E06*

*e06*\
&nbsp;&nbsp;&nbsp;&nbsp;*E06* *mulop* *E07* | *E06* *kaydırıcı üst* *E07* | *E07*

*e07*\
&nbsp;&nbsp;&nbsp;&nbsp;*E07* *ADDOP* *E08* | *E08*

*e08*\
&nbsp;&nbsp;&nbsp;&nbsp;**yüksek** *E09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **düşük** *E09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Highword** *E09*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Lowword** *E09*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E09*

*e09*\
&nbsp;&nbsp; **&nbsp;&nbsp;** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SEG** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Lroffset** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| **tür** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;**Bu** *E10* | \
&nbsp;&nbsp;&nbsp;&nbsp;| *E09* **PTR** *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E09* : *E10*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E10*

*e10*\
&nbsp;&nbsp;&nbsp;&nbsp;*E10* . *e11*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E10* ⟦ *Expr* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| *E11*

*e11*\
&nbsp;&nbsp;&nbsp;&nbsp;( *Expr* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| ⟦ *Expr* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **Genişlik** *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **maske** *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Boyut** *sizearg*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SIZEOF** *sizearg*\
&nbsp;&nbsp;&nbsp;&nbsp;| **uzunluk** *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **lengthıd** *id*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Recordconst*\
&nbsp;&nbsp;&nbsp;&nbsp;| *dize*\
&nbsp;&nbsp;&nbsp;&nbsp;| *sabit*\
&nbsp;&nbsp;&nbsp;&nbsp;| *tür*\
&nbsp;&nbsp;&nbsp;&nbsp;| *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **$**\
&nbsp;&nbsp;&nbsp;&nbsp;| *segmentRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;| *kaydet*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ST**\
&nbsp;&nbsp;&nbsp;&nbsp;| **St** ( *Expr* )

*yankı dizini*\
&nbsp;&nbsp;&nbsp;&nbsp;**ECHO**\
&nbsp;&nbsp;&nbsp;&nbsp;*yönetiliyor Raryıtext* ;; \
% **,** *yönetiliyor raryıtext* ;; \

*Elseifblock*\
&nbsp;&nbsp;&nbsp;&nbsp;*Elseifdeyim;* ; \
&nbsp;&nbsp;&nbsp;&nbsp;*Directivelist*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Elseifblock* ⟧ \

*Elseifdeyim\*
&nbsp;&nbsp;&nbsp;&nbsp;**ElseIf** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFE** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIFB** *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Elseifnb** *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Elseifdef** *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Elseifndef** *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Elseifdıf** *textıtem* , *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Elseifdifi** *textıtem* , *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Elseıfidn** *textıtem* , *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Elseifidnı** *textıtem* , *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIF1**\
&nbsp;&nbsp;&nbsp;&nbsp;| **ELSEIF2**

*Enddir*\
&nbsp;&nbsp;&nbsp;&nbsp;**End** ⟦ *immExpr* ⟧;;

*Endpdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*procId* **endp** ;;

*Endsdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği* **bitiyor** ;;

*Equdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Textmacroıd* **eşittir** *equttype* ;;

*Equtürü*\
&nbsp;&nbsp;&nbsp;&nbsp;*immExpr* | *textliteral*

*Errordir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Erroropt* ;;

*Erroropt*\
&nbsp;&nbsp;&nbsp;&nbsp; **. ERR** ⟦ *textıtem* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRE** *constExpr* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRNZ** *constExpr* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRB** *textıtem* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRNB** *textıtem* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRDEF** *kimliği* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRNDEF** *kimliği* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRDıF** *textıtem* , *textıtem* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRDıFI** *textıtem* , *textıtem* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRIDN** *textıtem* , *textıtem* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERRı** dili *textıtem* , *textıtem* ⟦ *seçenekmetni* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERR1** ⟦ *textıtem* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. ERR2** ⟦ *textıtem* ⟧

*Exitdir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. EXIT** &nbsp;&nbsp;&nbsp;&nbsp;⟦ *Expr* ⟧;;

*Exitmdir*\
&nbsp;&nbsp;&nbsp;&nbsp;: EXITD | *Exitmtextıtem*

*üs*\
&nbsp;&nbsp;&nbsp;&nbsp;E ⟦ *Sign* ⟧ *decnumber*

*expr*\
&nbsp;&nbsp;&nbsp;&nbsp;**Short** *E05*\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. TÜR** E01 \
&nbsp;&nbsp;&nbsp;&nbsp;| **Opattr** *E01*\
&nbsp;&nbsp;&nbsp;&nbsp;| *E01*

*exprList*\
&nbsp;&nbsp;&nbsp;&nbsp;*expr* | *exprList* , *Expr*

*externDef*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Langtype* ⟧ *ID* ⟦ ( *Altıd* ) ⟧: *externType*

*externDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*externKey* *externList* ;;

*externKey*\
&nbsp;&nbsp;&nbsp;&nbsp;**EXTRN** | **extern** | **externdef**

*externList*\
&nbsp;&nbsp;&nbsp;&nbsp;*externDef* | *externList* , ⟦;; ⟧ *externDef*

*externType*\
&nbsp;&nbsp;&nbsp;&nbsp;**ABS** | *qualifiedtype*

*Fieldalign*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*Fieldinit*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *InitValue* ⟧ | *Structınstance*

*Fieldinitlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Fieldinit* | *Fieldinitlist* , ⟦;; ⟧ *Fieldinit*

*Filechar*\
&nbsp;&nbsp;&nbsp;&nbsp;*sınırlayıcı*

*Filecharlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*filechar* | *filecharlist* *filechar*

*dosyabelirtimi*\
&nbsp;&nbsp;&nbsp;&nbsp;*Filecharlist* | *textliteral*

*FlagName*\
&nbsp;&nbsp; **&nbsp;&nbsp;.** | **mi?** | **taşma mı?** | **imzala?****eşlik  | ?**

*Floatnumarası*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *işareti* ⟧ *decnumber* . ⟦ *Decnumber* ⟧ ⟦ *üs* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| *rakamlar* R | *basamak* r

*Forcdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**forc** | **IRPC**

*Fordir*\
 | **IRP** **için** &nbsp;&nbsp;&nbsp;&nbsp;

*Forpara*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* ⟦: *Forparmtype* ⟧

*Forparmtype*\
&nbsp;&nbsp;&nbsp;&nbsp;**REQ** | = *Textliteral*

*Fpuregister*\
&nbsp;&nbsp;&nbsp;&nbsp;**St** *Expr*

*Frameexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;**SEG** *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **DGROUP** : *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| *segmentRegister* : *ID*\
&nbsp;&nbsp;&nbsp;&nbsp;| *kimliği*

*generaldir*\
&nbsp;&nbsp;&nbsp;&nbsp;*modeldir* | *Segorderdir* | *namedir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *ıncludelibdir* | *commentdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Groupdir* | *assumeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Structdir* | *Recorddir* | *typedefdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *externDir* | *Publicdir* | *Commdir* | *prototypedir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Equdir* | = Dir | *Textdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Contextdir* | *Optiondir* | *processordir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Radixdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Titledir* | *Pagedir* | *listdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Crefdir* | *yankı dizini*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Ifdir* | *Errordir* | *includeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Macrodir* | makro *çağrısı* | *macroRepeat* *purgeDir* | \
| *Macroforc* için * | &nbsp;* &nbsp;*macroFor* &nbsp; | &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;| *diğerad dir*

*Gpregister*\
&nbsp;&nbsp;&nbsp;&nbsp;AX | EAX | CX | ECX | DX | EDX | BX | EBX | DI | EDı | SI | ESI | BP | EBP | SP | ESP | RSP | R8W | R8D | R9W | R9D | R12D | R13W | R13D | R14W | R14D

*Groupdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*GroupID* **grubu** *segIdList*

*GroupID*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*onaltılık*\
&nbsp;&nbsp;&nbsp;&nbsp;b | c | d | e | f | A | B | C | D | E | Vadeli

*kimlik*\
&nbsp;&nbsp;&nbsp;&nbsp;, tanımlayıcının ilk karakteri büyük veya küçük harfli alfabetik bir karakter (`[A–Za-z]`) veya şu dört karakterden herhangi biri olabilir: `@ _ $ ?` kalan karakterler bu karakterlerden herhangi biri veya ondalık basamak olabilir (`[0–9]`). Maksimum uzunluk 247 karakterdir.

*ıdlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği* | *ıdlist* , *ID*

*ıdizinim*\
&nbsp;&nbsp;&nbsp;&nbsp;*Ifdeyimin* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*Directivelist*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Elseifblock* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ **Else** ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*Directivelist* ⟧;; \

*Ifdeyim\*
&nbsp;&nbsp; **&nbsp;&nbsp;** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFE** *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFB** *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ifnb** *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IFDEF** *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ifndef** *kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ifdıf** *textıtem* , *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Ifdifi** *textıtem* , *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ıfidn** *textıtem* , *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **ıfidnı** *textıtem* , *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **IF1**\
&nbsp;&nbsp;&nbsp;&nbsp;| **IF2**

*immExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;*Expr*

*includeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;**içerme** *;;*

*ıncludelibdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**ıncludelib** *dosyabelirtimi* ;;

*InitValue*\
&nbsp;&nbsp;&nbsp;&nbsp;*immExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| *dize*\
&nbsp;&nbsp;&nbsp;&nbsp;|? \
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *scalarinstlist* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| *Floatnumber*\
&nbsp;&nbsp;&nbsp;&nbsp;| *bcdConst*

*ınsegdir*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Labeldef* ⟧ *inSegmentDir*

*ınsegdirlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*ınsegdir* | *ınsegdirlist* *ınsegdir*

*inSegmentDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*yönerge*\
&nbsp;&nbsp;&nbsp;&nbsp;| *datadir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Controldir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Startupdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Exitdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *offsetDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Labeldir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *procdir* ⟦ *localdirlist* ⟧ ⟦ *ınsegdirlist* ⟧ *endpdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *ınvokedir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *generaldir*

*ınstrprefix*\
&nbsp;&nbsp;&nbsp;&nbsp;**REP** | **repe** | **repz** | **repne** | **repnz** | **Lock**

*yönerge*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *ınstrprefix* ⟧ *asminstruction*

*ınvokearg*\
&nbsp;&nbsp;&nbsp;&nbsp;*register* :: *yazmaç* | *Expr* | **addr** *Expr*

*ınvokedir*\
&nbsp;&nbsp;&nbsp;&nbsp;**Invoke** *Expr* ⟦, ⟦;; ⟧ *ınvokelist* ⟧;;

*ınvokelist*\
&nbsp;&nbsp;&nbsp;&nbsp;*ınvokearg* | *ınvokelist* , ⟦;; ⟧ *ınvokearg*

*anahtar sözcük*\
Tüm ayrılmış kelimeyi &nbsp;&nbsp;&nbsp;&nbsp;.

*Keywordlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*anahtar* sözcüğü | *anahtar sözcüğü* *keywordlist*

*Labeldef*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği* : | *kimlik* :: | @@:

*Labeldir*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimlik* **etiketi** *qualifiedtype* ;;

*Langtype*\
&nbsp;&nbsp;&nbsp;&nbsp;**C** | **Pascal** | **FORTRAN** | **temel** | **syscall** | **stdcall**

*Listdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Lidurme* ;;

*\*
&nbsp;&nbsp;&nbsp;&nbsp; **. LISTE**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. NOLIST**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. XLIST**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. LISTALL**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. LıSTıF**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. LFCOND**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. NOLıSTıF**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. SFCOND**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. TFCOND**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. LISTMAKROALL** |  **. LALL**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. NOLISTMACRO** |  **. SALL**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. LISTMACRO** |  **. XALL**\

*Localdef*\
&nbsp;&nbsp;&nbsp;&nbsp;**Yerel** *ıdlist* ;;

*yereldir*\
&nbsp;&nbsp;&nbsp;&nbsp;**Yerel** *ParmList* ;;

*Localdirlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*localdir* | *localdirlist* *localdir*

*Locallist*\
&nbsp;&nbsp;&nbsp;&nbsp;*localdef* | *locallist* *localdef*

*makro bağımsız*\
 % *constExpr*\
&nbsp;&nbsp;&nbsp;&nbsp;| %*Textmacroıd*\
&nbsp;&nbsp;&nbsp;&nbsp;| %*Macrofuncıd* ( *makroarglist* ) \
&nbsp;&nbsp;&nbsp;&nbsp;| *dize*\
&nbsp;&nbsp;&nbsp;&nbsp;| *yönetiliyor Raryıtext*\
&nbsp;&nbsp;&nbsp;&nbsp;| < *aracı* >

*Macroarglist*\
&nbsp;&nbsp;&nbsp;&nbsp;*macroarg* | *macroarglist* , *macroarg*

*makro gövdesi*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *locallist* ⟧ *macrostmtlist*

*makro çağrısı*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimlik* *makroarglist* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *kimliği* ( *makroarglist* )

*makro*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimlik* **makrosu** ⟦ *macroparmlist* ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*makro gövdesi*\
&nbsp;&nbsp;&nbsp;&nbsp;**Enda** ;;

\ *makrosu*
&nbsp;&nbsp;&nbsp;&nbsp;*Fordir* *forpard* , < *macroarglist* >;; \
&nbsp;&nbsp;&nbsp;&nbsp;*makro gövdesi*\
&nbsp;&nbsp;&nbsp;&nbsp;**Enda** ;;

*Macroforc*\
&nbsp;&nbsp;&nbsp;&nbsp;*Forcdir* *ID* , *textliteral* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*makro gövdesi*\
&nbsp;&nbsp;&nbsp;&nbsp;**Enda** ;;

*Macrofuncıd*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*makro kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;*Macroprocıd* | *macrofuncıd*

*Macroıdlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*macroıd* | *macroıdlist* , *macroıd*

*makro etiketi*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*makro*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* ⟦: *parmtype* ⟧

*Makroparmlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*macroParm* | *Macroparmlist* , ⟦;; ⟧ *Macropara*

*makro procId*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*makro yineleme*\
&nbsp;&nbsp;&nbsp;&nbsp;*Repeatdir* *constExpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*makro gövdesi*\
&nbsp;&nbsp;&nbsp;&nbsp;**Enda** ;;

*Macrostmt*\
&nbsp;&nbsp;&nbsp;&nbsp;*yönergesi* \
&nbsp;&nbsp;&nbsp;&nbsp;| *Exitmdir*\
&nbsp;&nbsp;&nbsp;&nbsp;| : *makro etiketi*\
&nbsp;&nbsp;&nbsp;&nbsp;| **git**\
&nbsp;&nbsp;&nbsp;&nbsp;*makro etiketi*

*makro Stmtlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Macrostmt* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *Macrostmtlist* *makrostmt* ;; \

*makro*\
&nbsp;&nbsp; **&nbsp;&nbsp;** *constExpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*makro gövdesi*\
&nbsp;&nbsp;&nbsp;&nbsp;**Enda** ;;

*MapType*\
&nbsp;&nbsp;&nbsp;&nbsp;**tüm** | **yok** | **NotPublic**

*Memoption*\
&nbsp;&nbsp;&nbsp;&nbsp;**küçük** | **küçük** | **orta** | **Compact** | **büyük | çok büyük** ** | ** **düz**

*anımsatıcı*\
&nbsp;&nbsp;&nbsp;&nbsp;yönerge adı.

*modeldir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. MODEL**\
&nbsp;&nbsp;&nbsp;&nbsp;*Memoption* ⟦, *Modeloplıst* ⟧;;

*Modelopt*\
&nbsp;&nbsp;&nbsp;&nbsp;*Langtype* | *stackoption*

*Modeloplıst*\
&nbsp;&nbsp;&nbsp;&nbsp;*modelopt* | *Modeloptlist* , *modelopt*

*modül*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Directivelist* ⟧ *enddir*

*Mulop*\
&nbsp;&nbsp;&nbsp;&nbsp;\* | / | **Mod**

*Namedir*\
&nbsp;&nbsp;&nbsp;&nbsp;**adı**\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği* ;; \

en *yakın*\
&nbsp;&nbsp;&nbsp;&nbsp;**yakın** | **FAR**

*Nestedstruct*\
&nbsp;&nbsp;&nbsp;&nbsp;*Structhdr* ⟦ *ID* ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*Structbody*\
&nbsp;&nbsp;&nbsp;&nbsp;**bitiyor** ;; \

*offsetDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*offsetDirType* ;;

*offsetDirType*\
&nbsp;&nbsp;&nbsp;&nbsp;**eşit** | **org** *immExpr* | **ALIGN** ⟦ *constExpr* ⟧

*offsetType*\
&nbsp;&nbsp;&nbsp;&nbsp;**grup** | **segmenti** | **düz**

*Oldrecordfieldlist*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *constExpr* ⟧ | *Oldrecordfieldlist* , ⟦ *constExpr* ⟧

*Optiondir*\
&nbsp;&nbsp;&nbsp;&nbsp;**OPTION** *optionlist* ;;

*Optionıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;**CaseMap** : *MapType*\
&nbsp;&nbsp;&nbsp;&nbsp;| **Dotname** | **nodotname**\
&nbsp;&nbsp;&nbsp;&nbsp;| **öykünücü** | **noemulator**\
&nbsp;&nbsp;&nbsp;&nbsp;| **Epıg** : *makro kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **EXPR16** | **EXPR32**\
&nbsp;&nbsp;&nbsp;&nbsp;| **dil** : *langtype*\
&nbsp;&nbsp;&nbsp;&nbsp;| **LJMP**
| **NOLJMP**\
&nbsp;&nbsp;&nbsp;&nbsp;| **M510** | **NOM510**\
&nbsp;&nbsp;&nbsp;&nbsp;| **Noanahtar sözcük** : < *keywordlist* >\
&nbsp;&nbsp;&nbsp;&nbsp;| **Nosignextend**\
&nbsp;&nbsp;&nbsp;&nbsp;| **fark** : *offsetType*\
&nbsp;&nbsp;&nbsp;&nbsp;| **oldmacros** | **nooldmacros**\
&nbsp;&nbsp;&nbsp;&nbsp;| **oldyapılar** | **nooldyapılar**\
&nbsp;&nbsp;&nbsp;&nbsp;| **proc** : *ovisibility*\
&nbsp;&nbsp;&nbsp;&nbsp;| **prolog** : *makro kimliği*\
&nbsp;&nbsp;&nbsp;&nbsp;| **READONLY** | **noreadonly**\
&nbsp;&nbsp;&nbsp;&nbsp;| **kapsamlı** | **nokapsamlıdır**\
&nbsp;&nbsp;&nbsp;&nbsp;| **segment** : *segsize*\
&nbsp;&nbsp;&nbsp;&nbsp;| **SETIF2** : bool

*seçenek listesi*\
&nbsp;&nbsp;&nbsp;&nbsp;*Optionıtem* | *optionlist* , ⟦;; ⟧ *Optionıtem*

*Seçenekmetni*\
&nbsp;&nbsp;&nbsp;&nbsp;, *Textıtem*

*Orop*\
&nbsp;&nbsp;&nbsp;&nbsp;**veya** | **Xor**

*Ovisibility*\
&nbsp;&nbsp;&nbsp;&nbsp;**ortak** | **özel** | **dışa aktarma**

*Pagedir*\
&nbsp;&nbsp;&nbsp;&nbsp;**Page** ⟦ *pageexpr* ⟧;;

*Pageexpr*\
&nbsp;&nbsp;&nbsp;&nbsp;\+ | ⟦ *Pagelength* ⟧ ⟦, *PageWidth* ⟧

*Pagelength*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*PageWidth*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*para*\
&nbsp;&nbsp;&nbsp;&nbsp;*ParmId* ⟦: *qualifiedtype* ⟧ | *Parmid* ⟦ *constExpr* ⟧ ⟦: *qualifiedtype* ⟧

*Parmid*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*ParmList*\
&nbsp;&nbsp;&nbsp;&nbsp;*para* | *ParmList* , ⟦;; ⟧ *para*

*Parmtype*\
&nbsp;&nbsp;&nbsp;&nbsp;**REQ** | = *Textliteral* | **vararg**

*pOptions*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *uzaklık* ⟧ ⟦ *Langtype* ⟧ ⟦ *ovisibility* ⟧

*birincil*\
&nbsp;&nbsp;&nbsp;&nbsp;*Expr* *BinaryOp* *Expr* | *FlagName* | *Expr*

*Procdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*procId* **proc**\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *pOptions* ⟧ ⟦ < *macroarglist* > ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Usesregs* ⟧ ⟦ *Procparmlist* ⟧

*işlemci*\
&nbsp;&nbsp;&nbsp;&nbsp;|. 386 |. 386p |. 486 |. 486P \
&nbsp;&nbsp;&nbsp;&nbsp;|. 586 |. 586P |. 686 |. 686P |. 387

*Processordir*\
&nbsp;&nbsp;&nbsp;&nbsp;*işlemcisi* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *Eşişlemcisi* ;;

*procId*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*Procıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;*ınstrprefix* | *datadir* | *Labeldir* | *offsetDir* | *generaldir*

*Procparmlist*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *ParmList* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *Parmid* : vararg ⟧

*Protoarg*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *ID* ⟧: *qualifiedtype*

*Protoarglist*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ *Protolist* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, ⟦;; ⟧ ⟦ *ID* ⟧: vararg ⟧

*Protolist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Protodeğişken*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Protolist* , ⟦;; ⟧ *Protoarg*

*Protospec*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *uzaklık* ⟧ ⟦ *Langtype* ⟧ ⟦ *protoarglist* ⟧ | *TypeId*

*Prototypedir*\
&nbsp;&nbsp;&nbsp;&nbsp;*ID* **proto** *protospec*

*Pubdef*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Langtype* ⟧ *ID*

*Publicdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**ortak** *publist* ;;

*publist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Pubdef* | *publist* , ⟦;; ⟧ *Pubdef*

*purgeDir*\
&nbsp;&nbsp;&nbsp;&nbsp;temizlik *makrosunu* **Temizleme**

*Qualifiedtype*\
&nbsp;&nbsp;&nbsp;&nbsp;*türü* | ⟦ *Distance* ⟧ **PTR** ⟦ *qualifiedtype* ⟧

*niteleyici*\
&nbsp;&nbsp;&nbsp;&nbsp;*Qualifiedtype* | **proto** *protospec*

*teklif*\
&nbsp;&nbsp;&nbsp;&nbsp;"| '

*Qwordregister*\
&nbsp;&nbsp;&nbsp;&nbsp;ÇX | RCX | RDX | RBX | RDı | RSı | RBP | R8 | R9 | R10 | R11 | R12 | R13 | R14 | R15

*Radixdir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. RADIX** *constExpr* ;;

*Radixoverride*\
&nbsp;&nbsp;&nbsp;&nbsp;h | o | soru-cevap | t | y | H | O | Soru-cevap | T | Iz

*Recordconst*\
&nbsp;&nbsp;&nbsp;&nbsp;*Recordtag* { *oldrecordfieldlist* } | *Recordtag* < *Oldrecordfieldlist* >

*Recorddir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Recordtag* **kayıt** *bitdeflist* ;;

*Recordfieldlist*\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *constExpr* ⟧ | *Recordfieldlist* , ⟦;; ⟧ ⟦ *constExpr* ⟧

*Recordınstance*\
 {⟦;; ⟧ *Recordfieldlist* ⟦;; ⟧} \
&nbsp;&nbsp;&nbsp;&nbsp;| < *Oldrecordfieldlist* >\
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *recordınstance* )

*Recordinstlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Recordınstance* | *recordınstlist* , ⟦;; ⟧ *Recordınstance*

*Recordtag*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*kayıt*\
&nbsp;&nbsp;&nbsp;&nbsp;*Specialregister* | *Gpregmi* | *Byteregister* | *Qwordregister* |  *fpuregister* | *simdregister* | *segmentRegister*

*Reglist*\
&nbsp;&nbsp;&nbsp;&nbsp;*kaydet* | *reglist* *kaydı*

*RelOp*\
&nbsp;&nbsp;&nbsp;&nbsp;EQ | NE BIR | LT | LE | GT | BIrLEŞTIr

*Repeatblock*\
&nbsp;&nbsp;&nbsp;&nbsp; **. YINELE** ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*blok deyimleri* ;; untilDir;;

*Repeatdir*\
&nbsp;&nbsp;&nbsp;&nbsp;**yinele** | **Yinele**

*Scalarinstlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*ınitvalue* | *Scalarinstlist* , ⟦;; ⟧ *InitValue*

\ *Hizala*
&nbsp;&nbsp;&nbsp;&nbsp;**bayt** | **WORD** | **DWORD** | **para** | **sayfası**

*Segattrib*\
&nbsp;&nbsp;&nbsp;&nbsp;**genel** | **Stack** | , *constExpr* | PRIVATE **üzerinde** **ortak** | **PRIVATE** **bellek** | 

*Segdir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. KOD**\
&nbsp;&nbsp;&nbsp;&nbsp;⟦ *Segıd* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. VERI**\
&nbsp;&nbsp;&nbsp;&nbsp;|   **. VERILER mi?** \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. CONST**\
&nbsp;&nbsp;&nbsp;&nbsp;|  **. FARDATA**⟦ *segıd* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|   **. FARVERI?** ⟦ *Segıd* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;|  **. STACK** ⟦ *constExpr* ⟧

*Segıd*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*segIdList*\
&nbsp;&nbsp;&nbsp;&nbsp;*Segıd*\
&nbsp;&nbsp;&nbsp;&nbsp;| *segIdList* , *segıd*

*segmentDef*\
&nbsp;&nbsp;&nbsp;&nbsp;*segmentDir* ⟦ *ınsegdirlist* ⟧ *Endsdir* | *simplesegdir* ⟦ *ınsegdirlist* ⟧ ⟦ *endsdir* ⟧

*segmentDir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Segıd* **segmenti** ⟦ *segoptionlist* ⟧;;

*segmentRegister*\
&nbsp;&nbsp;&nbsp;&nbsp;**CS** | **DS** | **lar** | **FS** | **GS** | **SS**

*Segoption*\
&nbsp;&nbsp;&nbsp;&nbsp;*Segalign*\
&nbsp;&nbsp;&nbsp;&nbsp;| *segRO*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Segattrib*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Segsize*\
&nbsp;&nbsp;&nbsp;&nbsp;| *ClassName*

*Segoptionlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*segoption* | *segoptionlist* *segoption*

*Segorderdir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. Alfa** |  **. SıRA** |  **. DOSSEG** | **DOSSEG**

*segRO*\
&nbsp;&nbsp;&nbsp;&nbsp;**ReadOnly**

*Segsize*\
&nbsp;&nbsp;&nbsp;&nbsp;**USE16** | **USE32** | **düz**

*kaydırıcı üst*\
&nbsp;&nbsp;&nbsp;&nbsp;**SHR** | **SHL**

\ *imzala*
 - | +

*Simdregister*\
&nbsp;&nbsp;&nbsp;&nbsp;MM0 | MM1 | MM2 | MM3 | MM4 | MM5 | MM6 | MM7 | xmmRegister | YMM0 ILA | YMM1 | YMM2 | YMM3 | YMM4 | YMM5 ARASıNDA | YMM6 | YMM7 | YMM8 | YMM9 | YMM10 | YMM11 | YMM12 | YMM13 | YMM14 | YMM15

*Simpleexpr*\
 ( *cexpr* ) | *birincil*

*Simplesegdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Segdir* ;;

*Sizliye g*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği* | *tür* | *E10*

*specialChars*\
 : | . | ⟦ | ⟧ | ( | ) | < | > | { | } \
&nbsp;&nbsp;&nbsp;&nbsp;| + | - | / | * | & | % | !\
&nbsp;&nbsp;&nbsp;&nbsp;| ' | \ | = | ; | , | "\
&nbsp;&nbsp;&nbsp;&nbsp;| *Whitespacecharacter*\
&nbsp;&nbsp;&nbsp;&nbsp;| *EndOfLine*

*Specialregister*\
&nbsp;&nbsp;&nbsp;&nbsp;CR0 | CR2 | CR3 | DR0 | DR1 | DR2 | DR3 | DR6 | DR7 | TR3 | TR4 | TR5 | TR6 | TR7

*Stackoption*\
&nbsp;&nbsp;&nbsp;&nbsp;**yaklaştığında yığın** | **farstack**

*Startupdir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. BAŞLANGıÇ** ;;

*stext*\
&nbsp;&nbsp;&nbsp;&nbsp;*stringchar* | *stext* *stringchar*

*dize*\
&nbsp;&nbsp;&nbsp;&nbsp;*quote* ⟦ *stext* ⟧ *quote*

*Stringchar*\
&nbsp;&nbsp;&nbsp;&nbsp;*teklif* *teklifi* | Tırnak işareti dışında herhangi bir karakter.

*Structbody*\
&nbsp;&nbsp;&nbsp;&nbsp;*Structıtem* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;| *Structbody* *structıtem* ;;

*Structdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Structtag* *structhdr* ⟦ *fieldalıgn* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;⟦, **Unique olmayan** ⟧;; \
&nbsp;&nbsp;&nbsp;&nbsp;*Structbody*\
&nbsp;&nbsp;&nbsp;&nbsp;*Structtag*\
&nbsp;&nbsp;&nbsp;&nbsp;**bitiyor** ;;

*Structhdr*\
&nbsp;&nbsp;&nbsp;&nbsp;**STRUC** | **struct** | **UNION**

*Structınstance*\
 < ⟦ *Fieldinitlist* ⟧ > \
&nbsp;&nbsp;&nbsp;&nbsp;| {⟦;; ⟧ ⟦ *Fieldinitlist* ⟧ ⟦;; ⟧} \
&nbsp;&nbsp;&nbsp;&nbsp;| *constExpr* **DUP** ( *structinstlist* ) \

*Structinstlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Structınstance* | *structinstlist* , ⟦;; ⟧ *Structınstance*

*Structıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;*datadir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *generaldir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *offsetDir*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Nestedstruct*

*Structtag*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*terim*\
&nbsp;&nbsp;&nbsp;&nbsp;*Simpleexpr* |! *simpleExpr*

*metin*\
&nbsp;&nbsp;&nbsp;&nbsp;*Textliteral* | *metin* karakteri |! *karakter* *metni* | *karakteri* |! *karakter*

*Textdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği* *textmacrodir* ;;

*Textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;*Textliteral* | *textmacroıd* | % *constExpr*

*Textlen*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*Textlist*\
&nbsp;&nbsp;&nbsp;&nbsp;*Textıtem* | *textlist* , ⟦;; ⟧ *Textıtem*

*Textliteral*\
&nbsp;&nbsp;&nbsp;&nbsp;< *metin* >;;

*Textmacrodir*\
&nbsp;&nbsp;&nbsp;&nbsp;**Catstr** ⟦ *textlist* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **TEXTEQU** ⟦ *textlist* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **Sizestr** *textıtem*\
&nbsp;&nbsp;&nbsp;&nbsp;| **substr** *textıtem* , *Textstart* ⟦, *textlen* ⟧ \
&nbsp;&nbsp;&nbsp;&nbsp;| **InStr** ⟦ *textstart* , ⟧ *textıtem* , *textıtem*

*Textmacroıd*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*Textstart*\
&nbsp;&nbsp;&nbsp;&nbsp;*constExpr*

*Titledir*\
&nbsp;&nbsp;&nbsp;&nbsp;*Titletype* ile *raryıtext* ;;

*Titletype*\
&nbsp;&nbsp;&nbsp;&nbsp;**başlık** | alt **başlık** | **alt TTL**

*tür*\
&nbsp;&nbsp;&nbsp;&nbsp;*Structtag*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Uniontag*\
&nbsp;&nbsp;&nbsp;&nbsp;| *Recordtag*\
&nbsp;&nbsp;&nbsp;&nbsp;| *uzaklık*\
&nbsp;&nbsp;&nbsp;&nbsp;| *veri türü*\
&nbsp;&nbsp;&nbsp;&nbsp;| *TypeId*

*Typedefdir*\
&nbsp;&nbsp;&nbsp;&nbsp;*TypeId* **typedef** niteleyicisi

*typeıd*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*Uniontag*\
&nbsp;&nbsp;&nbsp;&nbsp;*kimliği*

*Untildir*\
&nbsp;&nbsp;&nbsp;&nbsp; **. UNTIL** , *cexpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp; **. UNTILCXZ** ⟦ *cxzexpr* ⟧;;

*Usesregs*\
&nbsp;&nbsp;&nbsp;&nbsp;**USES** *reglist* kullanır

*Whileblock*\
&nbsp;&nbsp;&nbsp;&nbsp; **.\**
&nbsp;&nbsp;&nbsp;&nbsp;*cexpr* ;; \
&nbsp;&nbsp;&nbsp;&nbsp;*Blockdeyimlerini* ;; \
&nbsp;&nbsp;&nbsp;&nbsp; **. ENDW**

*Whitespacecharacter*\
&nbsp;&nbsp;&nbsp;&nbsp;ASCII 8, 9, 11 – 13, 26, 32

*Xmmregister*\
&nbsp;&nbsp;&nbsp;&nbsp;XMM0 | XMM1 | XMM2 | XMM3 | XMM4 | XMM5 | XMM6 | XMM7 | XMM8 | XMM9 | XMM10 | XMM11 | XMM12 | XMM13 | XMM14 | XMM15\
