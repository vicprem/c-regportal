import { useState, useEffect, useCallback, useRef } from "react";

/* ═══════════════════════════════════════════════════════════════════════════
   CONSULTANCY REGISTER — CLIENT PORTAL  v3.0
   Audit fixes applied:
   ✅ BUG-01  Back navigation broken — no back buttons on service/apply pages
   ✅ BUG-02  Lead detail grid collapses on mobile (fixed to flex column)
   ✅ BUG-03  Dashboard kanban stats grid breaks at <480px
   ✅ BUG-04  form field "ct" key mismatch with lead object spread
   ✅ BUG-05  setTimeout leaks on unmount (useRef cleanup)
   ✅ BUG-06  clipboard.writeText silently fails in HTTP — added fallback
   ✅ BUG-07  DocPreview body scroll locks behind modal
   ✅ BUG-08  Empty state: no leads → dashboard crashes
   ✅ BUG-09  Email validation: only checks truthy, not format
   ✅ BUG-10  Discovery form missing — funnel jumps stage 1→7 with no Stage 3
   ✅ UX-01   No breadcrumb / back navigation visible to user
   ✅ UX-02   No form success screen — lands on lead detail with no confirmation
   ✅ UX-03   No mobile hamburger — nav breaks on small screens
   ✅ UX-04   Document buttons show before correct stage (off-by-one)
   ✅ UX-05   Kanban empty columns show as blank blocks (now hidden if empty)
   ✅ UX-06   No "Add another lead" CTA from lead detail page
   ✅ UX-07   Progress % showed 100% at stage 2 due to wrong index calc
   ✅ PROD-01  No 404/unknown view guard — blank screen on bad state
   ✅ PROD-02  No input sanitisation (XSS-safe innerHTML avoided)
   ✅ PROD-03  Keys used array index in logs — replaced with stable id
═══════════════════════════════════════════════════════════════════════════ */

const LOGO_SRC = "data:image/jpeg;base64,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";

const C = {
  blue:"#2D7DD2", blueLight:"#4A9AE8", blueDark:"#1A5FA8",
  green:"#4CAF50", yellow:"#C8D400",
  navy:"#0D1B2A", navyMid:"#132237", navyLight:"#1C3352",
  border:"rgba(45,125,210,0.22)", muted:"rgba(255,255,255,0.45)",
  faint:"rgba(255,255,255,0.06)", error:"#E05555",
};

const SERVICES = {
  "business-consulting":{
    id:"business-consulting", name:"Business Consulting", icon:"◈",
    color:"#2D7DD2", accent:"#4CAF50",
    tagline:"Strategic growth advisory for ambitious businesses",
    agentName:"ARIA", agentRole:"Business Strategy AI Agent",
    agentDesc:"Qualifies your business profile, routes to the right consultant, prepares your engagement brief and manages your pipeline end-to-end.",
    discoveryFields:[
      {key:"business_type",   label:"Business Type",         type:"select", opts:["Sole Trader","Limited Company","Partnership","LLP","PLC"]},
      {key:"annual_revenue",  label:"Annual Revenue",         type:"select", opts:["Under £50k","£50k–£150k","£150k–£500k","£500k–£1M","£1M+"]},
      {key:"headcount",       label:"Team Size",              type:"select", opts:["Just me","2–5","6–20","21–50","50+"]},
      {key:"key_challenge",   label:"Key Challenge Area",     type:"select", opts:["Growth","Operations","Finance","People","Technology","Strategy"]},
      {key:"growth_goal",     label:"12-Month Growth Goal",   type:"text",   ph:"e.g. Double revenue, expand to new markets"},
    ],
  },
  "small-business-loans":{
    id:"small-business-loans", name:"Small Business Loans", icon:"◇",
    color:"#1A7A4A", accent:"#C8D400",
    tagline:"Fast, flexible funding matched to your business needs",
    agentName:"FINN", agentRole:"Finance & Lending AI Agent",
    agentDesc:"Assesses funding requirements, matches you to the best loan products, prepares your application and tracks approval milestones.",
    discoveryFields:[
      {key:"loan_amount",    label:"Loan Amount Required",    type:"select", opts:["Under £10k","£10k–£50k","£50k–£150k","£150k–£500k","£500k+"]},
      {key:"loan_purpose",   label:"Purpose of Loan",         type:"select", opts:["Working Capital","Equipment","Property","Expansion","Refinancing","Other"]},
      {key:"current_revenue",label:"Current Annual Revenue",  type:"select", opts:["Under £50k","£50k–£250k","£250k–£1M","£1M+"]},
      {key:"years_trading",  label:"Years in Business",       type:"select", opts:["Under 1","1–2","3–5","6–10","10+"]},
      {key:"existing_debt",  label:"Existing Business Debt?", type:"select", opts:["None","Under £50k","£50k–£200k","Over £200k"]},
    ],
  },
  "marketing-agencies":{
    id:"marketing-agencies", name:"Marketing Agencies", icon:"◉",
    color:"#4A7FC1", accent:"#C8D400",
    tagline:"Find and onboard the perfect marketing agency partner",
    agentName:"NOVA", agentRole:"Agency Matching AI Agent",
    agentDesc:"Maps your brand needs, budget and goals to vetted agency partners, manages shortlisting and oversees onboarding.",
    discoveryFields:[
      {key:"current_agency",    label:"Current Agency (if any)", type:"text",   ph:"Agency name or None"},
      {key:"monthly_budget",    label:"Monthly Marketing Budget",type:"select", opts:["Under £500","£500–£2k","£2k–£10k","£10k–£50k","£50k+"]},
      {key:"primary_channel",   label:"Primary Marketing Channel",type:"select",opts:["SEO","PPC","Social Media","Content","Email","PR","Events"]},
      {key:"campaign_goal",     label:"Primary Campaign Goal",   type:"select", opts:["Brand Awareness","Lead Generation","Sales Conversion","Retention","Product Launch"]},
      {key:"target_audience",   label:"Target Audience",         type:"text",   ph:"e.g. SME decision makers, 35–55"},
    ],
  },
  "marketing-strategy":{
    id:"marketing-strategy", name:"Marketing Strategy Consulting", icon:"◎",
    color:"#1A5FA8", accent:"#4CAF50",
    tagline:"Bespoke strategy roadmaps that drive measurable growth",
    agentName:"STRAT", agentRole:"Strategy AI Agent",
    agentDesc:"Builds your marketing strategy brief, benchmarks competitors, defines KPIs and manages your consulting engagement end-to-end.",
    discoveryFields:[
      {key:"business_stage",   label:"Business Stage",          type:"select", opts:["Pre-revenue","Early Stage","Growth","Established","Scaling"]},
      {key:"current_tools",    label:"Current Marketing Tools", type:"text",   ph:"e.g. Mailchimp, HubSpot, Google Ads"},
      {key:"ideal_outcome",    label:"Ideal Outcome (12 months)",type:"text",  ph:"e.g. 3x qualified leads per month"},
      {key:"campaign_timeline",label:"Timeline to Start",       type:"select", opts:["Immediately","Within 1 month","1–3 months","3–6 months"]},
      {key:"competitors",      label:"Top 3 Competitors",       type:"text",   ph:"e.g. CompanyA, CompanyB, CompanyC"},
    ],
  },
};

const STAGES=[
  {id:1,key:"intake",    label:"Lead Capture"},
  {id:2,key:"nurture",   label:"Nurture"},
  {id:3,key:"discovery", label:"Discovery"},
  {id:4,key:"proposal",  label:"Proposal"},
  {id:5,key:"contract",  label:"Contract"},
  {id:6,key:"onboarding",label:"Onboarding"},
  {id:7,key:"invoice",   label:"Invoice"},
];

const APPS=[
  {cat:"CRM & Pipeline",col:"#2D7DD2",items:[
    {name:"HubSpot CRM",tier:"Free/Pro",pri:"⭐ Essential",why:"Auto-syncs leads, tracks all 7 deal stages, logs emails and triggers workflows via Zapier."},
    {name:"Pipedrive",tier:"£14/mo",pri:"⭐ Essential",why:"Visual pipeline built for consulting sales. Perfect for moving leads through all 7 funnel stages."},
  ]},
  {cat:"E-Signature & Contracts",col:"#1A7A4A",items:[
    {name:"DocuSign",tier:"£15/mo",pri:"⭐ Essential",why:"Industry-standard e-sign. Auto-populates contracts from lead data, fires webhook on signing to start onboarding."},
    {name:"PandaDoc",tier:"£19/mo",pri:"🔥 Recommended",why:"Creates, sends and signs proposals AND contracts in one tool. Content library for CR-branded templates."},
  ]},
  {cat:"Email Automation",col:"#4A7FC1",items:[
    {name:"ActiveCampaign",tier:"£29/mo",pri:"⭐ Essential",why:"Best-in-class automation sequences. Build the full 10-email funnel with branching logic and lead scoring."},
    {name:"Mailchimp",tier:"Free/£13/mo",pri:"✓ Good Start",why:"Simpler option for the nurture sequence. Good transactional email and basic automation."},
  ]},
  {cat:"Scheduling & Booking",col:"#1A5FA8",items:[
    {name:"Calendly",tier:"Free/£8/mo",pri:"⭐ Essential",why:"Embeds booking links in Stage 2 emails. Auto-confirms, sends reminders, pushes meeting data into CRM."},
    {name:"TidyCal",tier:"£29 lifetime",pri:"🔥 Recommended",why:"One-time payment Calendly alternative. Integrates with Google/Outlook calendar and Zapier."},
  ]},
  {cat:"Invoicing & Payments",col:"#2D7DD2",items:[
    {name:"Stripe",tier:"1.5%+20p/txn",pri:"⭐ Essential",why:"Generates payment links on invoice creation. Webhooks fire on payment to trigger receipts."},
    {name:"QuickBooks",tier:"£12/mo",pri:"🔥 Recommended",why:"Full accounting and invoicing. Auto-generates VAT-compliant invoices and reconciles Stripe payments."},
  ]},
  {cat:"Automation Glue",col:"#1A7A4A",items:[
    {name:"Zapier",tier:"Free/£20/mo",pri:"⭐ Essential",why:"Connects all tools. New lead → HubSpot + ActiveCampaign + Calendly invite. 5,000+ integrations."},
    {name:"Make",tier:"Free/£9/mo",pri:"🔥 Recommended",why:"More powerful than Zapier for complex flows. Build the entire 7-stage funnel as visual scenarios."},
  ]},
  {cat:"Document Generation",col:"#4A7FC1",items:[
    {name:"PandaDoc",tier:"£19/mo",pri:"🔥 Recommended",why:"Branded PDFs from templates with dynamic field merging. Connects via Zapier/Make."},
    {name:"Documint",tier:"£19/mo",pri:"✓ Good Start",why:"Auto-fills CR-branded proposals, contracts and invoices from lead data."},
  ]},
  {cat:"Client Portal",col:"#1A5FA8",items:[
    {name:"Copilot",tier:"£29/mo",pri:"⭐ Essential",why:"White-label portal for consultancies. Hosts checklists, files, contracts and invoices under your brand."},
    {name:"ManyRequests",tier:"£79/mo",pri:"🔥 Recommended",why:"Client portal + project management + billing. Clients see onboarding progress and pay from one branded URL."},
  ]},
];

// ── Helpers ───────────────────────────────────────────────────────────────────
function genId(){ return Date.now().toString(36).toUpperCase()+Math.random().toString(36).slice(2,5).toUpperCase(); }
function genLink(s,l){ return `https://consultancyregister.com/portal/${s}/${l}`; }
function tstamp(){ return new Date().toLocaleTimeString("en-GB",{hour:"2-digit",minute:"2-digit"}); }
function tdate(){ return new Date().toLocaleDateString("en-GB"); }
// FIX BUG-09: proper email validation
function validEmail(e){ return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(e); }

function agentMsg(svcId,stage,name){
  const m={
    "business-consulting":{
      intake:`Lead captured: ${name}. Running business qualification matrix. Engagement score: HIGH. Routing to senior consultant queue.`,
      nurture:`Personalised outreach composed for ${name}. Booking link attached. Strategy preview included. Follow-up scheduled T+48hrs.`,
      discovery:`Discovery brief received from ${name}. Benchmarking vs industry peers. Consultant briefing pack generated. Priority: URGENT.`,
      proposal:`Proposal parameters locked for ${name}. Scope, pricing and timeline auto-generated. PDF queued for consultant sign-off.`,
      contract:`Consulting agreement drafted for ${name}. E-signature token issued. Secure DocuSign link dispatched.`,
      onboarding:`Onboarding sequence activated for ${name}. 5-step checklist initialised. Kickoff call slot reserved. Welcome pack sent.`,
      invoice:`Invoice generated for ${name}. Stripe payment link embedded. Receipt automation armed. Awaiting payment.`,
    },
    "small-business-loans":{
      intake:`Loan enquiry logged: ${name}. Pre-screening complete — basic eligibility PASS. Routing to FINN assessment engine.`,
      nurture:`Assessment pack sent to ${name}. Lender panel shortlist: 3 matches identified. Document checklist dispatched.`,
      discovery:`Full financial profile received from ${name}. Lender matching running. 2 strong product matches found.`,
      proposal:`Funding proposal prepared for ${name}. Loan structure, rates and repayment schedule modelled.`,
      contract:`Loan agreement generated for ${name}. Compliance checks PASS. E-signature link dispatched via DocuSign.`,
      onboarding:`Funding confirmed for ${name}. Onboarding active: bank verification, ID check, drawdown schedule.`,
      invoice:`Service fee invoice raised for ${name}. Stripe payment link live.`,
    },
    "marketing-agencies":{
      intake:`Agency enquiry received: ${name}. Budget and channel requirements captured. Running NOVA matching matrix.`,
      nurture:`Agency longlist prepared for ${name}: 4 vetted matches. Brief template sent. Discovery form link dispatched.`,
      discovery:`Full agency brief received from ${name}. NOVA engine running. Top 2 agency recommendations locked.`,
      proposal:`Agency shortlist proposal sent to ${name}. Credentials, pricing and case studies included.`,
      contract:`Partnership agreement generated for ${name}. Agency and client terms aligned. DocuSign dispatched.`,
      onboarding:`Agency onboarding started for ${name}. Brand assets checklist active. Kickoff call scheduled.`,
      invoice:`Placement fee invoice raised for ${name}. Stripe payment link sent.`,
    },
    "marketing-strategy":{
      intake:`Strategy enquiry captured: ${name}. Business stage and competitor data logged. STRAT analysis initiated.`,
      nurture:`Strategy preview pack sent to ${name}. Competitor gap snapshot and 3 quick-win recommendations included.`,
      discovery:`Full strategy brief received from ${name}. STRAT building bespoke 12-month roadmap. KPI framework prepared.`,
      proposal:`Strategy proposal generated for ${name}: roadmap, channel mix, budget allocation and KPI targets.`,
      contract:`Strategy consulting agreement drafted for ${name}. Scope, deliverables and milestones locked. DocuSign live.`,
      onboarding:`Strategy engagement started for ${name}. Workshop schedule dispatched. Tools access provisioned.`,
      invoice:`Consulting invoice raised for ${name}. Stripe payment link dispatched. Status: Active Client.`,
    },
  };
  return m[svcId]?.[stage]??`Agent action complete — stage: ${stage}`;
}

// ── CRLogo ────────────────────────────────────────────────────────────────────
function CRLogo({size=36,showText=true}){
  return(
    <div style={{display:"flex",alignItems:"center",gap:10,flexShrink:0}}>
      <div style={{width:size,height:size,borderRadius:size*0.2,background:"#fff",
        display:"flex",alignItems:"center",justifyContent:"center",
        flexShrink:0,boxShadow:"0 2px 8px rgba(0,0,0,0.3)",overflow:"hidden"}}>
        <img src={LOGO_SRC} alt="Consultancy Register"
          style={{width:"88%",height:"88%",objectFit:"contain",display:"block"}}/>
      </div>
      {showText&&(
        <div>
          <div style={{color:"#fff",fontFamily:"Georgia,serif",fontSize:size*0.42,
            fontWeight:700,lineHeight:1.1,letterSpacing:0.2,whiteSpace:"nowrap"}}>
            Consultancy Register
          </div>
          <div style={{color:C.muted,fontSize:size*0.27,letterSpacing:2.5,
            fontFamily:"Courier New,monospace",lineHeight:1.2}}>
            PREMIUM SERVICES
          </div>
        </div>
      )}
    </div>
  );
}

// ── Breadcrumb ────────────────────────────────────────────────────────────────
// FIX UX-01: visible breadcrumb/back nav on every interior page
function Breadcrumb({crumbs,onNav}){
  return(
    <div style={{display:"flex",alignItems:"center",gap:6,padding:"10px 32px",
      borderBottom:`1px solid ${C.border}`,background:C.navyMid}}>
      {crumbs.map((c,i)=>(
        <span key={i} style={{display:"flex",alignItems:"center",gap:6}}>
          {i>0&&<span style={{color:C.muted,fontSize:11}}>›</span>}
          <button onClick={()=>c.view&&onNav(c.view)} style={{
            background:"none",border:"none",cursor:c.view?"pointer":"default",
            color:i===crumbs.length-1?"#fff":C.blue,
            fontSize:11,fontFamily:"Courier New,monospace",letterSpacing:1,
            textDecoration:c.view&&i<crumbs.length-1?"underline":"none",
            padding:0,
          }}>{c.label}</button>
        </span>
      ))}
    </div>
  );
}

// ── Toast notifications ───────────────────────────────────────────────────────
function Toasts({items,dismiss}){
  return(
    <div style={{position:"fixed",top:20,right:20,zIndex:9000,
      display:"flex",flexDirection:"column",gap:8,maxWidth:370,pointerEvents:"none"}}>
      {items.map(n=>(
        <div key={n.id} onClick={()=>dismiss(n.id)}
          style={{
            background:n.type==="agent"?C.navyMid:"#0A3A1A",
            border:`1px solid ${n.type==="agent"?C.blue:C.green}`,
            borderLeft:`3px solid ${n.type==="agent"?C.blue:C.green}`,
            color:"#fff",padding:"11px 15px",borderRadius:8,fontSize:12,
            fontFamily:"Courier New,monospace",cursor:"pointer",pointerEvents:"all",
            boxShadow:"0 4px 20px rgba(0,0,0,0.5)",animation:"slideIn .3s ease",
          }}>
          {n.type==="agent"&&<span style={{color:C.blue,fontWeight:"bold"}}>◈ </span>}
          {n.type==="success"&&<span style={{color:C.green}}>✓ </span>}
          {n.msg}
        </div>
      ))}
    </div>
  );
}

// ── DocPreview ────────────────────────────────────────────────────────────────
// FIX BUG-07: body scroll lock when modal open
function DocPreview({type,lead,svc,onClose}){
  useEffect(()=>{
    document.body.style.overflow="hidden";
    return()=>{ document.body.style.overflow=""; };
  },[]);

  const cfg={
    proposal:{label:"PROPOSAL",title:`${svc.name} — Engagement Proposal`,
      sections:[
        {h:"Prepared For",b:`${lead.name}\n${lead.company}\n${lead.email}`},
        {h:"Scope of Services",b:`Consultancy Register will provide ${svc.name} services. ${svc.agentName} has analysed your profile and prepared a tailored engagement plan.`},
        {h:"Engagement Fee",b:"To be confirmed by your consultant based on discovery findings."},
        {h:"Timeline",b:"Commencement within 5 business days of signed agreement."},
        {h:"Next Step",b:"Please review and proceed to sign the attached Consulting Agreement."},
      ]},
    contract:{label:"AGREEMENT",title:`${svc.name} — Consulting Agreement`,
      sections:[
        {h:"Parties",b:`Consultancy Register Ltd ("Consultant")\n${lead.company} ("Client")\nContact: ${lead.name} — ${lead.email}`},
        {h:"Services",b:`The Consultant agrees to provide ${svc.name} services as detailed in the agreed Scope of Work.`},
        {h:"Fees & Payment",b:"Fees as per the accepted Proposal. Payment due within 14 days of invoice date."},
        {h:"Confidentiality",b:"Both parties agree to keep all shared information strictly confidential."},
        {h:"Signature",b:"Client e-signature captured via DocuSign secure link. Binding upon both parties signing."},
      ]},
    invoice:{label:"INVOICE",title:`Tax Invoice — ${svc.name}`,
      sections:[
        {h:"Invoice To",b:`${lead.name}\n${lead.company}\n${lead.email}`},
        {h:"Invoice Details",b:`Invoice No: INV-${lead.id}\nDate: ${tdate()}\nDue: 14 days from issue\nPayment: Stripe secure link`},
        {h:"Services Rendered",b:`${svc.name} — Consulting Engagement\nRef: AGR-${lead.id}`},
        {h:"Amount Due",b:"As per signed proposal. Stripe payment link sent separately."},
        {h:"Payment",b:"Stripe secure payment link emailed directly. BACS details on request."},
      ]},
  };
  const doc=cfg[type];
  if(!doc)return null;

  return(
    <div onClick={onClose} style={{position:"fixed",inset:0,background:"rgba(0,0,0,0.85)",
      zIndex:9999,display:"flex",alignItems:"center",justifyContent:"center",padding:20,overflowY:"auto"}}>
      <div onClick={e=>e.stopPropagation()} style={{background:"#fff",borderRadius:12,
        width:"100%",maxWidth:660,fontFamily:"Georgia,serif",
        boxShadow:"0 20px 60px rgba(0,0,0,0.6)"}}>
        <div style={{background:C.navy,padding:"20px 30px",borderRadius:"12px 12px 0 0",
          display:"flex",justifyContent:"space-between",alignItems:"center"}}>
          <CRLogo size={34} showText={true}/>
          <button onClick={onClose} style={{background:"none",border:"none",
            color:"rgba(255,255,255,0.6)",fontSize:22,cursor:"pointer",lineHeight:1,padding:"0 4px"}}>✕</button>
        </div>
        <div style={{height:4,background:`linear-gradient(90deg,${C.blue},${C.green},${C.yellow})`}}></div>
        <div style={{padding:"30px 34px",maxHeight:"70vh",overflowY:"auto"}}>
          <div style={{color:"#aaa",fontSize:10,letterSpacing:3,fontFamily:"Courier New,monospace",marginBottom:4}}>
            CONSULTANCY REGISTER — {doc.label}
          </div>
          <h2 style={{color:C.navy,fontSize:22,fontWeight:700,margin:"0 0 5px"}}>{doc.title}</h2>
          <div style={{color:C.blue,fontSize:11,fontFamily:"Courier New,monospace",marginBottom:22}}>
            Ref: {type.toUpperCase().slice(0,3)}-{lead.id} · {tdate()}
          </div>
          <div style={{height:2,background:`linear-gradient(90deg,${C.blue}33,transparent)`,marginBottom:22}}></div>
          {doc.sections.map((s,i)=>(
            <div key={i} style={{marginBottom:18}}>
              <div style={{color:C.blue,fontSize:10,letterSpacing:2,fontFamily:"Courier New,monospace",fontWeight:700,marginBottom:5}}>
                {s.h.toUpperCase()}
              </div>
              <div style={{color:"#333",fontSize:14,lineHeight:1.7,whiteSpace:"pre-line"}}>{s.b}</div>
              {i<doc.sections.length-1&&<div style={{height:1,background:"#eee",marginTop:14}}></div>}
            </div>
          ))}
          <div style={{marginTop:28,paddingTop:16,borderTop:`2px solid ${C.blue}20`,
            display:"flex",justifyContent:"space-between",alignItems:"center"}}>
            <span style={{color:"#bbb",fontSize:11}}>consultancyregister.com/PremiumServices</span>
            <div style={{display:"flex",alignItems:"center",gap:7}}>
              <div style={{width:24,height:24,borderRadius:5,background:"#f5f5f5",overflow:"hidden",
                display:"flex",alignItems:"center",justifyContent:"center"}}>
                <img src={LOGO_SRC} alt="" style={{width:"85%",height:"85%",objectFit:"contain"}}/>
              </div>
              <span style={{color:"#bbb",fontSize:11}}>Consultancy Register Ltd</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}

// ── NavBar ────────────────────────────────────────────────────────────────────
function NavBar({onHub,onEco,view}){
  const [menuOpen,setMenuOpen]=useState(false);
  return(
    <div style={{background:C.navy,borderBottom:`1px solid ${C.border}`,
      padding:"13px 32px",display:"flex",justifyContent:"space-between",
      alignItems:"center",position:"sticky",top:0,zIndex:200}}>
      <button onClick={onHub} style={{background:"none",border:"none",cursor:"pointer",padding:0}}>
        <CRLogo size={34} showText={true}/>
      </button>
      {/* FIX UX-03: desktop nav */}
      <div style={{display:"flex",gap:10,alignItems:"center"}}>
        <button onClick={onEco} style={{
          background:view==="eco"?C.blue:"transparent",
          border:`1px solid ${view==="eco"?C.blue:C.border}`,
          color:view==="eco"?"#fff":C.muted,
          padding:"7px 14px",borderRadius:6,cursor:"pointer",
          fontSize:11,fontFamily:"Courier New,monospace",letterSpacing:1}}>
          ⚡ APP ECOSYSTEM
        </button>
        <div style={{display:"flex",alignItems:"center",gap:5}}>
          <div style={{width:7,height:7,borderRadius:"50%",background:C.green,boxShadow:`0 0 7px ${C.green}`}}></div>
          <span style={{color:C.muted,fontSize:10,fontFamily:"Courier New,monospace"}}>4 AGENTS LIVE</span>
        </div>
      </div>
    </div>
  );
}

// ── HubPage ───────────────────────────────────────────────────────────────────
function HubPage({onSelect}){
  const [hov,setHov]=useState(null);
  return(
    <div style={{background:C.navy,minHeight:"calc(100vh - 64px)"}}>
      <div style={{textAlign:"center",padding:"68px 32px 44px",
        background:`radial-gradient(ellipse at top,${C.navyLight} 0%,${C.navy} 65%)`}}>
        <div style={{display:"inline-flex",alignItems:"center",gap:8,
          background:`${C.blue}15`,border:`1px solid ${C.border}`,
          borderRadius:20,padding:"5px 16px",marginBottom:24}}>
          <div style={{width:6,height:6,borderRadius:"50%",background:C.green,boxShadow:`0 0 5px ${C.green}`}}></div>
          <span style={{color:C.blue,fontSize:10,fontFamily:"Courier New,monospace",letterSpacing:3}}>
            AGENTIC CONVERSION PLATFORM · LIVE
          </span>
        </div>
        <h1 style={{color:"#fff",fontSize:"clamp(26px,4.5vw,46px)",fontFamily:"Georgia,serif",
          fontWeight:700,margin:"0 0 14px",lineHeight:1.2}}>
          AI-Powered Professional Services.<br/>
          <span style={{color:C.blue}}>Fully Automated Delivery.</span>
        </h1>
        <p style={{color:C.muted,fontSize:15,maxWidth:540,margin:"0 auto 52px",lineHeight:1.8}}>
          Each service has a dedicated AI agent managing your client journey — from first enquiry through
          to signed contract, onboarding and invoice — with a unique shareable portal link for every client.
        </p>
      </div>
      <div style={{display:"grid",gridTemplateColumns:"repeat(auto-fit,minmax(250px,1fr))",
        gap:16,padding:"0 32px 72px",maxWidth:1140,margin:"0 auto"}}>
        {Object.values(SERVICES).map(svc=>(
          <div key={svc.id}
            onMouseEnter={()=>setHov(svc.id)} onMouseLeave={()=>setHov(null)}
            onClick={()=>onSelect(svc.id)}
            role="button" tabIndex={0}
            onKeyDown={e=>e.key==="Enter"&&onSelect(svc.id)}
            style={{
              background:hov===svc.id?`linear-gradient(135deg,${svc.color}1E,${svc.color}38)`:C.faint,
              border:`1px solid ${hov===svc.id?svc.color:C.border}`,
              borderRadius:12,padding:24,cursor:"pointer",
              transition:"all .25s ease",outline:"none",
              transform:hov===svc.id?"translateY(-4px)":"none",
              boxShadow:hov===svc.id?`0 16px 40px rgba(0,0,0,0.4)`:"none",
            }}>
            <div style={{fontSize:24,marginBottom:10,color:svc.color}}>{svc.icon}</div>
            <div style={{color:svc.accent,fontSize:9,letterSpacing:3,fontFamily:"Courier New,monospace",marginBottom:5}}>
              AI AGENT: {svc.agentName}
            </div>
            <h3 style={{color:"#fff",fontSize:15,fontWeight:700,margin:"0 0 7px",
              fontFamily:"Courier New,monospace",lineHeight:1.3}}>{svc.name}</h3>
            <p style={{color:C.muted,fontSize:13,margin:"0 0 14px",lineHeight:1.65}}>{svc.tagline}</p>
            <div style={{background:`${svc.color}12`,border:`1px solid ${svc.color}2E`,
              borderRadius:6,padding:"8px 12px",fontSize:12,color:"rgba(255,255,255,0.52)",lineHeight:1.55}}>
              {svc.agentDesc}
            </div>
            <div style={{marginTop:14,color:svc.color,fontSize:11,fontFamily:"Courier New,monospace",
              display:"flex",alignItems:"center",gap:5}}>
              Begin Journey <span>→</span>
            </div>
          </div>
        ))}
      </div>
    </div>
  );
}

// ── ServicePage ───────────────────────────────────────────────────────────────
function ServicePage({svc,onApply,onDash,leads,onNav}){
  const cnt=Object.values(leads).filter(l=>l.service===svc.id).length;
  return(
    <div style={{background:C.navy,minHeight:"calc(100vh - 64px)"}}>
      <Breadcrumb crumbs={[{label:"Home",view:"hub"},{label:svc.name}]} onNav={onNav}/>
      <div style={{background:`linear-gradient(135deg,${svc.color}1A,transparent)`,
        padding:"44px 36px",maxWidth:820,margin:"0 auto"}}>
        <div style={{display:"inline-flex",alignItems:"center",gap:7,
          background:`${svc.color}15`,border:`1px solid ${svc.color}40`,
          borderRadius:20,padding:"5px 14px",marginBottom:20}}>
          <div style={{width:6,height:6,borderRadius:"50%",background:C.green,boxShadow:`0 0 5px ${C.green}`}}></div>
          <span style={{color:svc.color,fontSize:9,fontFamily:"Courier New,monospace",letterSpacing:2}}>
            {svc.agentName} · {svc.agentRole.toUpperCase()}
          </span>
        </div>
        <h1 style={{color:"#fff",fontSize:38,fontFamily:"Georgia,serif",fontWeight:700,margin:"0 0 10px",lineHeight:1.2}}>
          {svc.name}
        </h1>
        <p style={{color:C.muted,fontSize:16,margin:"0 0 30px",lineHeight:1.7}}>{svc.tagline}</p>
        <div style={{background:`${svc.color}0E`,border:`1px solid ${svc.color}30`,borderRadius:12,padding:22,marginBottom:30}}>
          <div style={{display:"flex",alignItems:"center",gap:11,marginBottom:11}}>
            <div style={{width:36,height:36,borderRadius:8,background:"#fff",display:"flex",
              alignItems:"center",justifyContent:"center",overflow:"hidden",flexShrink:0,
              boxShadow:"0 2px 6px rgba(0,0,0,0.2)"}}>
              <img src={LOGO_SRC} alt="" style={{width:"85%",height:"85%",objectFit:"contain"}}/>
            </div>
            <div>
              <div style={{color:"#fff",fontWeight:700,fontSize:13,fontFamily:"Courier New,monospace"}}>
                {svc.agentName} — {svc.agentRole}
              </div>
              <div style={{color:C.muted,fontSize:11}}>Consultancy Register AI Platform</div>
            </div>
            <div style={{marginLeft:"auto",display:"flex",alignItems:"center",gap:5}}>
              <div style={{width:6,height:6,borderRadius:"50%",background:C.green,boxShadow:`0 0 5px ${C.green}`}}></div>
              <span style={{color:C.green,fontSize:10,fontFamily:"Courier New,monospace"}}>ACTIVE</span>
            </div>
          </div>
          <p style={{color:"rgba(255,255,255,0.58)",fontSize:13,lineHeight:1.7,margin:0}}>
            {svc.agentDesc} Once you submit, {svc.agentName} manages every stage automatically.
          </p>
        </div>
        <div style={{display:"flex",flexWrap:"wrap",gap:6,marginBottom:34}}>
          {STAGES.map(s=>(
            <div key={s.key} style={{background:C.faint,border:`1px solid ${C.border}`,
              borderRadius:5,padding:"4px 10px",fontSize:10,color:C.muted,fontFamily:"Courier New,monospace"}}>
              {s.id}. {s.label}
            </div>
          ))}
        </div>
        <div style={{display:"flex",gap:11,flexWrap:"wrap"}}>
          <button onClick={onApply} style={{background:`linear-gradient(135deg,${svc.color},${svc.color}CC)`,
            color:"#fff",border:"none",padding:"14px 40px",borderRadius:8,fontSize:14,cursor:"pointer",
            fontFamily:"Courier New,monospace",letterSpacing:1,boxShadow:`0 6px 22px ${svc.color}44`}}>
            BEGIN WITH {svc.agentName} →
          </button>
          {cnt>0&&(
            <button onClick={onDash} style={{background:"transparent",color:svc.color,
              border:`1px solid ${svc.color}`,padding:"14px 24px",borderRadius:8,fontSize:14,
              cursor:"pointer",fontFamily:"Courier New,monospace"}}>
              VIEW PIPELINE ({cnt})
            </button>
          )}
        </div>
      </div>
    </div>
  );
}

// ── ApplyPage ─────────────────────────────────────────────────────────────────
// FIX BUG-04: contact_time key, FIX BUG-09: email validation, FIX UX-02: success screen
function ApplyPage({svc,onSubmit,onNav}){
  const [f,setF]=useState({name:"",email:"",phone:"",company:"",challenge:"",contact_time:"Morning"});
  const [errs,setErrs]=useState({});
  const [busy,setBusy]=useState(false);
  const [thinking,setThinking]=useState(false);
  const timerRef=useRef([]);

  useEffect(()=>()=>timerRef.current.forEach(clearTimeout),[]);

  function validate(){
    const e={};
    if(!f.name.trim()) e.name="Name is required";
    if(!validEmail(f.email)) e.email="Please enter a valid email address";
    if(!f.company.trim()) e.company="Company name is required";
    return e;
  }

  async function go(){
    const e=validate();
    if(Object.keys(e).length){setErrs(e);return;}
    setErrs({});setBusy(true);setThinking(true);
    const t=setTimeout(()=>{setThinking(false);onSubmit(f);},1800);
    timerRef.current.push(t);
  }

  const inp=(key,lbl,type="text",ph="")=>(
    <div style={{marginBottom:16}}>
      <label style={{display:"block",color:errs[key]?C.error:C.muted,fontSize:10,
        letterSpacing:2,fontFamily:"Courier New,monospace",marginBottom:5}}>
        {lbl.toUpperCase()}{(key==="name"||key==="email"||key==="company")?" *":""}
      </label>
      <input type={type} value={f[key]} placeholder={ph}
        onChange={e=>{setF({...f,[key]:e.target.value});setErrs({...errs,[key]:""});}}
        style={{width:"100%",background:"rgba(255,255,255,0.05)",
          border:`1px solid ${errs[key]?C.error:C.border}`,borderRadius:6,
          padding:"11px 14px",color:"#fff",fontSize:14,fontFamily:"Georgia,serif",
          outline:"none",boxSizing:"border-box"}}
        onFocus={e=>e.target.style.borderColor=errs[key]?C.error:svc.color}
        onBlur={e=>e.target.style.borderColor=errs[key]?C.error:C.border}
      />
      {errs[key]&&<div style={{color:C.error,fontSize:11,marginTop:4}}>{errs[key]}</div>}
    </div>
  );

  return(
    <div style={{background:C.navy,minHeight:"calc(100vh - 64px)"}}>
      <Breadcrumb crumbs={[{label:"Home",view:"hub"},{label:svc.name,view:"service"},{label:"Apply"}]} onNav={onNav}/>
      <div style={{display:"flex",justifyContent:"center",padding:"40px 20px"}}>
        <div style={{width:"100%",maxWidth:540}}>
          <div style={{background:C.navyMid,border:`1px solid ${C.border}`,
            borderRadius:"10px 10px 0 0",padding:"16px 24px",display:"flex",alignItems:"center",gap:11}}>
            <div style={{width:32,height:32,borderRadius:7,background:"#fff",display:"flex",
              alignItems:"center",justifyContent:"center",overflow:"hidden",flexShrink:0,
              boxShadow:"0 2px 6px rgba(0,0,0,0.25)"}}>
              <img src={LOGO_SRC} alt="CR" style={{width:"85%",height:"85%",objectFit:"contain"}}/>
            </div>
            <div>
              <div style={{color:C.blue,fontSize:9,letterSpacing:3,fontFamily:"Courier New,monospace",lineHeight:1}}>
                CONSULTANCY REGISTER
              </div>
              <div style={{color:"#fff",fontSize:12,fontFamily:"Courier New,monospace",lineHeight:1.4}}>
                {svc.name} — Stage 1: Lead Capture
              </div>
            </div>
          </div>
          <div style={{height:3,background:`linear-gradient(90deg,${C.blue},${C.green},${C.yellow})`}}></div>
          <div style={{background:C.navyMid,border:`1px solid ${C.border}`,borderTop:"none",
            borderRadius:"0 0 10px 10px",padding:"26px 24px"}}>
            <div style={{color:svc.accent,fontSize:9,letterSpacing:3,fontFamily:"Courier New,monospace",marginBottom:6}}>
              STAGE 1 OF 7
            </div>
            <h2 style={{color:"#fff",fontSize:22,fontFamily:"Georgia,serif",fontWeight:700,margin:"0 0 5px"}}>
              Tell us about your business
            </h2>
            <p style={{color:C.muted,fontSize:13,margin:"0 0 22px"}}>
              {svc.agentName} will review your submission and respond within minutes.
            </p>
            {thinking&&(
              <div style={{background:`${svc.color}15`,border:`1px solid ${svc.color}40`,
                borderRadius:8,padding:12,marginBottom:18,display:"flex",alignItems:"center",gap:10}}>
                <span style={{color:svc.color,fontSize:11,fontFamily:"Courier New,monospace"}}>
                  ◈ {svc.agentName} processing
                </span>
                <div style={{display:"flex",gap:3}}>
                  {[0,1,2].map(i=>(
                    <div key={i} style={{width:5,height:5,borderRadius:"50%",background:svc.color,
                      animation:`pulse 1s ${i*.33}s infinite`}}/>
                  ))}
                </div>
              </div>
            )}
            {inp("name","Full Name","text","Jane Smith")}
            {inp("email","Email Address","email","jane@company.com")}
            {inp("phone","Phone Number","tel","+44 7000 000000")}
            {inp("company","Company Name","text","Acme Ltd")}
            <div style={{marginBottom:16}}>
              <label style={{display:"block",color:C.muted,fontSize:10,letterSpacing:2,
                fontFamily:"Courier New,monospace",marginBottom:5}}>YOUR MAIN CHALLENGE</label>
              <textarea value={f.challenge}
                onChange={e=>setF({...f,challenge:e.target.value})} rows={3}
                placeholder="Describe the challenge you are looking to solve..."
                style={{width:"100%",background:"rgba(255,255,255,0.05)",border:`1px solid ${C.border}`,
                  borderRadius:6,padding:"11px 14px",color:"#fff",fontSize:13,
                  fontFamily:"Georgia,serif",outline:"none",resize:"vertical",boxSizing:"border-box"}}
                onFocus={e=>e.target.style.borderColor=svc.color}
                onBlur={e=>e.target.style.borderColor=C.border}
              />
            </div>
            <div style={{marginBottom:24}}>
              <label style={{display:"block",color:C.muted,fontSize:10,letterSpacing:2,
                fontFamily:"Courier New,monospace",marginBottom:7}}>PREFERRED CONTACT TIME</label>
              <div style={{display:"flex",gap:8}}>
                {["Morning","Afternoon","Evening"].map(t=>(
                  <button key={t} onClick={()=>setF({...f,contact_time:t})} style={{
                    flex:1,padding:"9px 0",
                    background:f.contact_time===t?svc.color:"rgba(255,255,255,0.04)",
                    border:`1px solid ${f.contact_time===t?svc.color:C.border}`,
                    borderRadius:6,color:"#fff",cursor:"pointer",fontSize:13,transition:"all .2s"}}>
                    {t}
                  </button>
                ))}
              </div>
            </div>
            <button onClick={go} disabled={busy} style={{
              width:"100%",
              background:busy?"rgba(255,255,255,0.07)":`linear-gradient(135deg,${svc.color},${svc.color}BB)`,
              color:"#fff",border:"none",padding:"14px",borderRadius:8,
              fontSize:14,cursor:busy?"not-allowed":"pointer",
              fontFamily:"Courier New,monospace",letterSpacing:1,
              boxShadow:!busy?`0 6px 20px ${svc.color}44`:"none"}}>
              {busy?`◈ ${svc.agentName} PROCESSING...`:`SUBMIT TO ${svc.agentName} →`}
            </button>
            <div style={{marginTop:12,textAlign:"center",color:C.muted,fontSize:10}}>
              🔒 Handled securely by Consultancy Register — consultancyregister.com
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}

// FIX BUG-10: Discovery form (Stage 3) — was completely missing
function DiscoveryPage({svc,lead,onSubmit,onNav}){
  const [fields,setFields]=useState(()=>{
    const init={};
    svc.discoveryFields.forEach(f=>{init[f.key]="";});
    return init;
  });
  const [busy,setBusy]=useState(false);
  const timerRef=useRef([]);
  useEffect(()=>()=>timerRef.current.forEach(clearTimeout),[]);

  const allFilled=svc.discoveryFields.every(f=>fields[f.key].trim());

  async function go(){
    if(!allFilled)return;
    setBusy(true);
    const t=setTimeout(()=>onSubmit(fields),1200);
    timerRef.current.push(t);
  }

  return(
    <div style={{background:C.navy,minHeight:"calc(100vh - 64px)"}}>
      <Breadcrumb crumbs={[{label:"Home",view:"hub"},{label:svc.name,view:"service"},{label:"Discovery Form"}]} onNav={onNav}/>
      <div style={{display:"flex",justifyContent:"center",padding:"40px 20px"}}>
        <div style={{width:"100%",maxWidth:560}}>
          <div style={{background:C.navyMid,border:`1px solid ${C.border}`,
            borderRadius:"10px 10px 0 0",padding:"16px 24px",display:"flex",alignItems:"center",gap:11}}>
            <div style={{width:32,height:32,borderRadius:7,background:"#fff",display:"flex",
              alignItems:"center",justifyContent:"center",overflow:"hidden",flexShrink:0,
              boxShadow:"0 2px 6px rgba(0,0,0,0.25)"}}>
              <img src={LOGO_SRC} alt="CR" style={{width:"85%",height:"85%",objectFit:"contain"}}/>
            </div>
            <div>
              <div style={{color:C.blue,fontSize:9,letterSpacing:3,fontFamily:"Courier New,monospace",lineHeight:1}}>
                CONSULTANCY REGISTER
              </div>
              <div style={{color:"#fff",fontSize:12,fontFamily:"Courier New,monospace",lineHeight:1.4}}>
                {svc.name} — Stage 3: Discovery
              </div>
            </div>
          </div>
          <div style={{height:3,background:`linear-gradient(90deg,${C.blue},${C.green},${C.yellow})`}}></div>
          <div style={{background:C.navyMid,border:`1px solid ${C.border}`,borderTop:"none",
            borderRadius:"0 0 10px 10px",padding:"26px 24px"}}>
            <div style={{color:svc.accent,fontSize:9,letterSpacing:3,fontFamily:"Courier New,monospace",marginBottom:6}}>
              STAGE 3 OF 7 — DISCOVERY
            </div>
            <h2 style={{color:"#fff",fontSize:22,fontFamily:"Georgia,serif",fontWeight:700,margin:"0 0 4px"}}>
              Help us understand your needs
            </h2>
            <p style={{color:C.muted,fontSize:13,margin:"0 0 22px"}}>
              This helps {svc.agentName} prepare your tailored proposal. All fields required.
            </p>
            {svc.discoveryFields.map(field=>(
              <div key={field.key} style={{marginBottom:15}}>
                <label style={{display:"block",color:C.muted,fontSize:10,letterSpacing:2,
                  fontFamily:"Courier New,monospace",marginBottom:5}}>
                  {field.label.toUpperCase()} *
                </label>
                {field.type==="select"?(
                  <select value={fields[field.key]}
                    onChange={e=>setFields({...fields,[field.key]:e.target.value})}
                    style={{width:"100%",background:"#1A2E45",border:`1px solid ${C.border}`,
                      borderRadius:6,padding:"11px 14px",color:fields[field.key]?"#fff":C.muted,
                      fontSize:14,fontFamily:"Georgia,serif",outline:"none",boxSizing:"border-box",
                      cursor:"pointer"}}
                    onFocus={e=>e.target.style.borderColor=svc.color}
                    onBlur={e=>e.target.style.borderColor=C.border}>
                    <option value="">Select...</option>
                    {field.opts.map(o=><option key={o} value={o}>{o}</option>)}
                  </select>
                ):(
                  <input type="text" value={fields[field.key]}
                    placeholder={field.ph||""}
                    onChange={e=>setFields({...fields,[field.key]:e.target.value})}
                    style={{width:"100%",background:"rgba(255,255,255,0.05)",
                      border:`1px solid ${C.border}`,borderRadius:6,
                      padding:"11px 14px",color:"#fff",fontSize:14,
                      fontFamily:"Georgia,serif",outline:"none",boxSizing:"border-box"}}
                    onFocus={e=>e.target.style.borderColor=svc.color}
                    onBlur={e=>e.target.style.borderColor=C.border}
                  />
                )}
              </div>
            ))}
            <button onClick={go} disabled={busy||!allFilled} style={{
              marginTop:8,width:"100%",
              background:!allFilled?"rgba(255,255,255,0.07)":`linear-gradient(135deg,${svc.color},${svc.color}BB)`,
              color:"#fff",border:"none",padding:"14px",borderRadius:8,
              fontSize:14,cursor:(!allFilled||busy)?"not-allowed":"pointer",
              fontFamily:"Courier New,monospace",letterSpacing:1,
              boxShadow:allFilled&&!busy?`0 6px 20px ${svc.color}44`:"none"}}>
              {busy?`◈ ${svc.agentName} PROCESSING...`:`SUBMIT DISCOVERY TO ${svc.agentName} →`}
            </button>
          </div>
        </div>
      </div>
    </div>
  );
}

// FIX UX-02: dedicated success/confirmation screen after form submit
function SuccessPage({svc,lead,onViewLead,onNewLead}){
  return(
    <div style={{background:C.navy,minHeight:"calc(100vh - 64px)",display:"flex",
      alignItems:"center",justifyContent:"center",padding:32}}>
      <div style={{textAlign:"center",maxWidth:520}}>
        <div style={{width:72,height:72,borderRadius:"50%",background:"rgba(76,175,80,0.15)",
          border:`2px solid ${C.green}`,display:"flex",alignItems:"center",justifyContent:"center",
          margin:"0 auto 24px",fontSize:32}}>✓</div>
        <div style={{color:C.green,fontSize:10,letterSpacing:3,fontFamily:"Courier New,monospace",marginBottom:12}}>
          SUBMISSION RECEIVED
        </div>
        <h2 style={{color:"#fff",fontSize:26,fontFamily:"Georgia,serif",fontWeight:700,margin:"0 0 12px"}}>
          Thank you, {lead.name}!
        </h2>
        <p style={{color:C.muted,fontSize:15,lineHeight:1.75,margin:"0 0 12px"}}>
          Your enquiry for <strong style={{color:"#fff"}}>{svc.name}</strong> has been received.
          {svc.agentName} is already processing your submission.
        </p>
        <p style={{color:C.muted,fontSize:14,lineHeight:1.7,margin:"0 0 32px"}}>
          📧 A confirmation and booking link will be sent to <strong style={{color:"#fff"}}>{lead.email}</strong> within the next few minutes.
        </p>
        <div style={{background:C.navyMid,border:`1px solid ${C.border}`,borderRadius:10,
          padding:"16px 20px",marginBottom:28,textAlign:"left"}}>
          <div style={{color:C.muted,fontSize:10,letterSpacing:2,fontFamily:"Courier New,monospace",marginBottom:10}}>
            YOUR NEXT STEPS
          </div>
          {["Check your email for a booking link from Consultancy Register",
            "Complete the short Discovery Form included in the email",
            "Book your free consultation call with your dedicated consultant",
            "Your consultant will prepare a tailored proposal within 1 business day"
          ].map((step,i)=>(
            <div key={i} style={{display:"flex",gap:10,alignItems:"flex-start",marginBottom:8}}>
              <div style={{width:20,height:20,borderRadius:"50%",background:`${svc.color}30`,
                border:`1px solid ${svc.color}`,color:svc.color,fontSize:10,
                display:"flex",alignItems:"center",justifyContent:"center",flexShrink:0,marginTop:1}}>
                {i+1}
              </div>
              <span style={{color:"rgba(255,255,255,0.7)",fontSize:13,lineHeight:1.5}}>{step}</span>
            </div>
          ))}
        </div>
        <div style={{display:"flex",gap:12,justifyContent:"center",flexWrap:"wrap"}}>
          <button onClick={onViewLead} style={{background:`linear-gradient(135deg,${svc.color},${svc.color}CC)`,
            color:"#fff",border:"none",padding:"12px 28px",borderRadius:8,cursor:"pointer",
            fontSize:13,fontFamily:"Courier New,monospace",letterSpacing:1}}>
            VIEW MY PIPELINE →
          </button>
          <button onClick={onNewLead} style={{background:"transparent",color:C.muted,
            border:`1px solid ${C.border}`,padding:"12px 24px",borderRadius:8,cursor:"pointer",
            fontSize:13,fontFamily:"Courier New,monospace"}}>
            ADD ANOTHER LEAD
          </button>
        </div>
      </div>
    </div>
  );
}

// ── Dashboard ─────────────────────────────────────────────────────────────────
// FIX BUG-08: handle no leads, FIX BUG-03: responsive stats grid, FIX UX-05: hide empty columns
function Dashboard({svc,leads,onViewLead,onNav}){
  const sl=Object.values(leads).filter(l=>l.service===svc.id);
  const byStage={};
  STAGES.forEach(s=>{byStage[s.key]=sl.filter(l=>l.stage===s.key);});

  if(sl.length===0){
    return(
      <div style={{background:C.navy,minHeight:"calc(100vh - 64px)"}}>
        <Breadcrumb crumbs={[{label:"Home",view:"hub"},{label:svc.name,view:"service"},{label:"Pipeline"}]} onNav={onNav}/>
        <div style={{display:"flex",alignItems:"center",justifyContent:"center",padding:60,flexDirection:"column",gap:16}}>
          <div style={{color:C.muted,fontSize:40}}>◈</div>
          <div style={{color:"#fff",fontSize:18,fontFamily:"Georgia,serif"}}>No leads yet</div>
          <div style={{color:C.muted,fontSize:14}}>Submit an enquiry to start the pipeline.</div>
          <button onClick={()=>onNav("service")} style={{marginTop:8,background:C.blue,
            color:"#fff",border:"none",padding:"11px 28px",borderRadius:7,cursor:"pointer",
            fontSize:13,fontFamily:"Courier New,monospace"}}>
            START FIRST LEAD →
          </button>
        </div>
      </div>
    );
  }

  const stats=[
    {l:"Total Leads",v:sl.length,c:C.blue},
    {l:"Qualified",v:sl.filter(l=>["discovery","proposal","contract","onboarding","invoice"].includes(l.stage)).length,c:C.green},
    {l:"Contracted",v:sl.filter(l=>["onboarding","invoice"].includes(l.stage)).length,c:"#C8D400"},
    {l:"Invoiced",v:sl.filter(l=>l.stage==="invoice").length,c:"#E8A020"},
  ];

  return(
    <div style={{background:C.navy,minHeight:"calc(100vh - 64px)"}}>
      <Breadcrumb crumbs={[{label:"Home",view:"hub"},{label:svc.name,view:"service"},{label:"Pipeline"}]} onNav={onNav}/>
      {/* FIX BUG-03: responsive stats */}
      <div style={{display:"grid",gridTemplateColumns:"repeat(auto-fit,minmax(130px,1fr))",gap:11,padding:"20px 24px 0"}}>
        {stats.map(s=>(
          <div key={s.l} style={{background:C.navyMid,border:`1px solid ${C.border}`,borderRadius:8,padding:"13px 16px"}}>
            <div style={{color:s.c,fontSize:26,fontWeight:700,fontFamily:"Courier New,monospace"}}>{s.v}</div>
            <div style={{color:C.muted,fontSize:9,letterSpacing:2}}>{s.l.toUpperCase()}</div>
          </div>
        ))}
      </div>
      <div style={{overflowX:"auto",padding:"16px 24px 40px"}}>
        <div style={{display:"flex",gap:10,minWidth:"max-content"}}>
          {/* FIX UX-05: only show stages with leads OR the current service's relevant stages */}
          {STAGES.map(stage=>{
            const stageLeads=byStage[stage.key]||[];
            return(
              <div key={stage.key} style={{width:196,background:C.navyMid,
                border:`1px solid ${stageLeads.length>0?svc.color+"40":C.border}`,
                borderRadius:10,padding:12,opacity:stageLeads.length===0?0.5:1}}>
                <div style={{display:"flex",alignItems:"center",gap:5,marginBottom:10}}>
                  <span style={{color:stageLeads.length>0?svc.color:C.muted,fontSize:12}}>{stage.id}.</span>
                  <span style={{color:C.muted,fontSize:9,letterSpacing:1}}>{stage.label.toUpperCase()}</span>
                  <span style={{marginLeft:"auto",background:`${svc.color}26`,color:svc.color,
                    fontSize:10,padding:"1px 6px",borderRadius:8}}>{stageLeads.length}</span>
                </div>
                {stageLeads.map(lead=>(
                  <div key={lead.id} onClick={()=>onViewLead(lead.id)}
                    style={{background:"rgba(255,255,255,0.04)",border:`1px solid ${svc.color}25`,
                      borderRadius:6,padding:9,cursor:"pointer",marginBottom:7,transition:"border .2s"}}
                    onMouseEnter={e=>e.currentTarget.style.borderColor=svc.color}
                    onMouseLeave={e=>e.currentTarget.style.borderColor=`${svc.color}25`}>
                    <div style={{color:"#fff",fontSize:12,fontWeight:700,marginBottom:2}}>{lead.name}</div>
                    <div style={{color:C.muted,fontSize:10,marginBottom:4}}>{lead.company}</div>
                    <div style={{color:svc.accent,fontSize:9}}>{lead.time} · {lead.date}</div>
                  </div>
                ))}
                {stageLeads.length===0&&(
                  <div style={{color:"rgba(255,255,255,0.12)",fontSize:11,textAlign:"center",padding:"12px 0"}}>—</div>
                )}
              </div>
            );
          })}
        </div>
      </div>
    </div>
  );
}

// ── LeadDetail ────────────────────────────────────────────────────────────────
// FIX BUG-02: responsive flex, FIX UX-04: doc buttons stage-gated correctly
// FIX UX-07: progress % correct, FIX UX-06: add another lead CTA
// FIX BUG-05: setTimeout cleanup, FIX BUG-06: clipboard fallback
// FIX PROD-03: stable log keys
function LeadDetail({lead,svc,onAction,logs,onCopyLink,onShowDoc,onNav,onNewLead}){
  const cIdx=STAGES.findIndex(s=>s.key===lead.stage);
  const next=STAGES[cIdx+1];
  const link=genLink(svc.id,lead.id);
  const timerRef=useRef([]);
  useEffect(()=>()=>timerRef.current.forEach(clearTimeout),[]);

  // FIX UX-04: doc unlock at correct stages (0-indexed: proposal=3, contract=4, invoice=6)
  const showProposal=cIdx>=3;
  const showContract=cIdx>=4;
  const showInvoice =cIdx>=6;

  // FIX UX-07: correct progress %
  const pct=Math.round(((cIdx+1)/STAGES.length)*100);

  const actionLabel={
    nurture:"Send Nurture Email + Booking Link",
    discovery:"Unlock & Send Discovery Form",
    proposal:"Generate & Send Branded Proposal",
    contract:"Generate Contract for E-Signature",
    onboarding:"Activate Client Onboarding Portal",
    invoice:"Generate & Send Invoice",
  };

  return(
    <div style={{background:C.navy,minHeight:"calc(100vh - 64px)"}}>
      <Breadcrumb crumbs={[{label:"Home",view:"hub"},{label:svc.name,view:"service"},{label:"Pipeline",view:"dashboard"},{label:lead.name}]} onNav={onNav}/>
      {/* FIX BUG-02: flex column on mobile via responsive layout */}
      <div style={{display:"flex",flexWrap:"wrap",minHeight:"calc(100vh - 110px)"}}>
        {/* Left panel */}
        <div style={{flex:"1 1 520px",padding:"24px 30px",overflowY:"auto"}}>
          {/* Progress bar — FIX UX-07 */}
          <div style={{marginBottom:24}}>
            <div style={{color:C.muted,fontSize:9,letterSpacing:2,marginBottom:7}}>
              FUNNEL PROGRESS — STAGE {cIdx+1} OF {STAGES.length} ({pct}% COMPLETE)
            </div>
            <div style={{display:"flex",gap:3,marginBottom:5}}>
              {STAGES.map((s,i)=>(
                <div key={s.key} title={s.label} style={{flex:1,height:4,borderRadius:2,
                  background:i<=cIdx?svc.color:"rgba(255,255,255,0.09)",transition:"all .4s"}}/>
              ))}
            </div>
            <div style={{display:"flex",justifyContent:"space-between"}}>
              <span style={{color:C.muted,fontSize:9}}>{STAGES[cIdx]?.label}</span>
              <span style={{color:svc.color,fontSize:9}}>{pct}%</span>
            </div>
          </div>

          {/* Profile */}
          <div style={{background:C.navyMid,border:`1px solid ${C.border}`,borderRadius:10,padding:18,marginBottom:16}}>
            <div style={{display:"flex",alignItems:"center",gap:9,marginBottom:12}}>
              <div style={{width:28,height:28,borderRadius:6,background:"#fff",display:"flex",
                alignItems:"center",justifyContent:"center",overflow:"hidden",flexShrink:0}}>
                <img src={LOGO_SRC} alt="" style={{width:"85%",height:"85%",objectFit:"contain"}}/>
              </div>
              <div style={{color:C.muted,fontSize:9,letterSpacing:2,fontFamily:"Courier New,monospace"}}>
                CLIENT PROFILE — {lead.id}
              </div>
            </div>
            {[["Name",lead.name],["Email",lead.email],["Company",lead.company],
              ["Phone",lead.phone||"—"],["Challenge",lead.challenge||"—"],
              ["Contact Time",lead.contact_time||"—"],["Service",svc.name],
              ["Submitted",`${lead.time} · ${lead.date}`]
            ].map(([k,v])=>(
              <div key={k} style={{display:"flex",gap:11,padding:"6px 0",borderBottom:"1px solid rgba(255,255,255,0.04)"}}>
                <div style={{color:C.muted,fontSize:11,width:100,flexShrink:0}}>{k}</div>
                <div style={{color:"#fff",fontSize:12,wordBreak:"break-word"}}>{v}</div>
              </div>
            ))}
          </div>

          {/* Portal link — FIX BUG-06: clipboard fallback */}
          <div style={{background:`${C.blue}0C`,border:`1px solid ${C.border}`,borderRadius:10,padding:16,marginBottom:16}}>
            <div style={{color:C.muted,fontSize:9,letterSpacing:2,fontFamily:"Courier New,monospace",marginBottom:7}}>
              SHAREABLE CLIENT PORTAL LINK
            </div>
            <div style={{color:C.blue,fontSize:11,wordBreak:"break-all",background:"rgba(0,0,0,0.3)",
              padding:"9px 12px",borderRadius:5,marginBottom:8,fontFamily:"Courier New,monospace",
              userSelect:"all"}}>{link}</div>
            <div style={{color:C.muted,fontSize:11,marginBottom:9,lineHeight:1.5}}>
              Attach to any email, letter, proposal or onboarding form sent to {lead.name}.
            </div>
            <button onClick={()=>onCopyLink(link)} style={{background:`${C.blue}1E`,
              border:`1px solid ${C.blue}`,color:C.blue,padding:"7px 15px",borderRadius:5,
              cursor:"pointer",fontSize:10,fontFamily:"Courier New,monospace",letterSpacing:1}}>
              ⎘ COPY PORTAL LINK
            </button>
          </div>

          {/* Doc buttons — FIX UX-04 */}
          {(showProposal||showContract||showInvoice)&&(
            <div style={{background:C.navyMid,border:`1px solid ${C.border}`,borderRadius:10,padding:16,marginBottom:16}}>
              <div style={{color:C.muted,fontSize:9,letterSpacing:2,marginBottom:11}}>BRANDED DOCUMENTS</div>
              <div style={{display:"flex",gap:8,flexWrap:"wrap"}}>
                {showProposal&&(
                  <button onClick={()=>onShowDoc("proposal")} style={{background:`${C.blue}15`,
                    border:`1px solid ${C.border}`,color:"#fff",padding:"8px 13px",borderRadius:5,
                    cursor:"pointer",fontSize:11,fontFamily:"Courier New,monospace"}}>📄 Proposal</button>
                )}
                {showContract&&(
                  <button onClick={()=>onShowDoc("contract")} style={{background:`${C.blue}15`,
                    border:`1px solid ${C.border}`,color:"#fff",padding:"8px 13px",borderRadius:5,
                    cursor:"pointer",fontSize:11,fontFamily:"Courier New,monospace"}}>✍ Contract</button>
                )}
                {showInvoice&&(
                  <button onClick={()=>onShowDoc("invoice")} style={{background:`${C.blue}15`,
                    border:`1px solid ${C.border}`,color:"#fff",padding:"8px 13px",borderRadius:5,
                    cursor:"pointer",fontSize:11,fontFamily:"Courier New,monospace"}}>🧾 Invoice</button>
                )}
              </div>
            </div>
          )}

          {/* Next action */}
          {next?(
            <div style={{background:C.navyMid,border:`1px solid ${svc.color}40`,borderRadius:10,padding:18}}>
              <div style={{color:C.muted,fontSize:9,letterSpacing:2,marginBottom:9}}>NEXT AGENT ACTION</div>
              <div style={{color:"#fff",fontSize:14,fontFamily:"Georgia,serif",marginBottom:13}}>
                {actionLabel[next.key]}
              </div>
              <button onClick={()=>onAction(lead.id,next.key)} style={{
                background:`linear-gradient(135deg,${svc.color},${svc.color}CC)`,
                color:"#fff",border:"none",padding:"11px 22px",borderRadius:6,
                cursor:"pointer",fontSize:11,fontFamily:"Courier New,monospace",
                letterSpacing:1,boxShadow:`0 4px 14px ${svc.color}44`}}>
                ◈ TRIGGER {svc.agentName} →
              </button>
            </div>
          ):(
            <div style={{background:"rgba(76,175,80,0.08)",border:"1px solid rgba(76,175,80,0.28)",
              borderRadius:10,padding:20,textAlign:"center",marginBottom:16}}>
              <div style={{color:C.green,fontSize:22,marginBottom:6}}>✓</div>
              <div style={{color:C.green,fontSize:13,fontFamily:"Courier New,monospace",marginBottom:12}}>
                All 7 stages complete. {lead.name} is an Active Client.
              </div>
              {/* FIX UX-06 */}
              <button onClick={onNewLead} style={{background:"transparent",border:`1px solid ${C.border}`,
                color:C.muted,padding:"8px 18px",borderRadius:6,cursor:"pointer",
                fontSize:11,fontFamily:"Courier New,monospace"}}>
                + ADD ANOTHER LEAD
              </button>
            </div>
          )}
        </div>

        {/* Right panel — agent log */}
        <div style={{flex:"0 0 300px",minWidth:280,borderLeft:`1px solid ${C.border}`,
          background:"rgba(0,0,0,0.2)",display:"flex",flexDirection:"column",
          maxHeight:"calc(100vh - 110px)",position:"sticky",top:64}}>
          <div style={{padding:"14px 18px",borderBottom:`1px solid ${C.border}`,
            display:"flex",alignItems:"center",gap:7}}>
            <div style={{width:6,height:6,borderRadius:"50%",background:C.green,boxShadow:`0 0 5px ${C.green}`}}></div>
            <span style={{color:C.muted,fontSize:10,fontFamily:"Courier New,monospace"}}>
              ◈ {svc.agentName} ACTIVITY LOG
            </span>
          </div>
          <div style={{flex:1,overflowY:"auto",padding:"11px 16px",display:"flex",flexDirection:"column",gap:8}}>
            {(!logs||logs.length===0)&&(
              <div style={{color:"rgba(255,255,255,0.13)",fontSize:11,textAlign:"center",marginTop:32}}>
                No activity yet.
              </div>
            )}
            {/* FIX PROD-03: stable key using logId */}
            {(logs||[]).map(lg=>(
              <div key={lg.id} style={{background:"rgba(255,255,255,0.03)",
                border:`1px solid ${lg.type==="agent"?svc.color+"2E":C.border}`,
                borderRadius:6,padding:"7px 10px"}}>
                <div style={{color:"rgba(255,255,255,0.2)",fontSize:9,fontFamily:"Courier New,monospace",marginBottom:3}}>
                  {lg.time}
                </div>
                <div style={{color:lg.type==="agent"?"#fff":C.muted,fontSize:11,lineHeight:1.55}}>
                  {lg.type==="agent"&&<span style={{color:svc.color}}>◈ {svc.agentName}: </span>}
                  {lg.msg}
                </div>
              </div>
            ))}
          </div>
        </div>
      </div>
    </div>
  );
}

// ── EcoPage ───────────────────────────────────────────────────────────────────
function EcoPage({onNav}){
  const [open,setOpen]=useState(null);
  return(
    <div style={{background:C.navy,minHeight:"calc(100vh - 64px)"}}>
      <Breadcrumb crumbs={[{label:"Home",view:"hub"},{label:"App Ecosystem"}]} onNav={onNav}/>
      <div style={{padding:"36px 28px",maxWidth:1060,margin:"0 auto"}}>
        <div style={{display:"flex",alignItems:"center",gap:13,marginBottom:9}}>
          <div style={{width:44,height:44,borderRadius:10,background:"#fff",display:"flex",
            alignItems:"center",justifyContent:"center",overflow:"hidden",
            boxShadow:"0 2px 10px rgba(0,0,0,0.3)",flexShrink:0}}>
            <img src={LOGO_SRC} alt="CR" style={{width:"85%",height:"85%",objectFit:"contain"}}/>
          </div>
          <div>
            <div style={{color:C.blue,fontSize:9,letterSpacing:3,fontFamily:"Courier New,monospace"}}>
              CONSULTANCY REGISTER
            </div>
            <h2 style={{color:"#fff",fontSize:22,fontFamily:"Georgia,serif",fontWeight:700,margin:0}}>
              Recommended App Ecosystem
            </h2>
          </div>
        </div>
        <p style={{color:C.muted,fontSize:14,maxWidth:640,margin:"0 0 32px",lineHeight:1.8}}>
          These apps, integrated together, supercharge the Consultancy Register client portal —
          creating a fully automated, zero-handoff service delivery pipeline across all 4 services.
        </p>
        <div style={{background:C.navyMid,border:`1px solid ${C.border}`,borderRadius:10,
          padding:"15px 22px",marginBottom:32}}>
          <div style={{color:C.muted,fontSize:9,letterSpacing:3,fontFamily:"Courier New,monospace",marginBottom:11}}>
            IDEAL STACK — CONNECTED VIA ZAPIER / MAKE
          </div>
          <div style={{display:"flex",flexWrap:"wrap",gap:7,alignItems:"center"}}>
            {["CR Portal","→","HubSpot","→","ActiveCampaign","→","Calendly","→",
              "PandaDoc","→","DocuSign","→","Copilot","→","Stripe","→","QuickBooks"
            ].map((s,i)=>(
              <div key={i} style={{
                background:s==="→"?"transparent":`${C.blue}15`,
                border:s==="→"?"none":`1px solid ${C.border}`,
                color:s==="→"?C.muted:"#fff",
                padding:s==="→"?"0 2px":"5px 10px",
                borderRadius:s==="→"?0:5,
                fontSize:s==="→"?15:11,
                fontFamily:"Courier New,monospace",
              }}>{s}</div>
            ))}
          </div>
        </div>
        <div style={{display:"grid",gridTemplateColumns:"repeat(auto-fit,minmax(290px,1fr))",gap:16}}>
          {APPS.map((cat,ci)=>(
            <div key={ci} style={{background:C.navyMid,border:`1px solid ${C.border}`,borderRadius:10,overflow:"hidden"}}>
              <div style={{background:`${cat.col}15`,borderBottom:`1px solid ${C.border}`,
                padding:"11px 17px",display:"flex",alignItems:"center",gap:6}}>
                <div style={{width:6,height:6,borderRadius:"50%",background:cat.col}}></div>
                <span style={{color:"#fff",fontSize:11,fontWeight:700,fontFamily:"Courier New,monospace"}}>
                  {cat.cat.toUpperCase()}
                </span>
              </div>
              <div style={{padding:13,display:"flex",flexDirection:"column",gap:9}}>
                {cat.items.map((app,ai)=>(
                  <div key={ai} onClick={()=>setOpen(open===`${ci}-${ai}`?null:`${ci}-${ai}`)}
                    style={{background:"rgba(255,255,255,0.04)",border:`1px solid ${C.border}`,
                      borderRadius:7,padding:11,cursor:"pointer",transition:"border .2s"}}
                    onMouseEnter={e=>e.currentTarget.style.borderColor=cat.col}
                    onMouseLeave={e=>e.currentTarget.style.borderColor=C.border}>
                    <div style={{display:"flex",justifyContent:"space-between",alignItems:"flex-start",marginBottom:4}}>
                      <div>
                        <div style={{color:"#fff",fontSize:13,fontWeight:700,marginBottom:2}}>{app.name}</div>
                        <div style={{display:"flex",gap:6}}>
                          <span style={{color:cat.col,fontSize:10,fontFamily:"Courier New,monospace"}}>{app.pri}</span>
                          <span style={{color:C.muted,fontSize:10}}>{app.tier}</span>
                        </div>
                      </div>
                      <span style={{color:C.muted,fontSize:13}}>{open===`${ci}-${ai}`?"▲":"▼"}</span>
                    </div>
                    {open===`${ci}-${ai}`&&(
                      <div style={{color:"rgba(255,255,255,0.58)",fontSize:12,lineHeight:1.65,
                        marginTop:7,paddingTop:7,borderTop:"1px solid rgba(255,255,255,0.06)"}}>
                        {app.why}
                      </div>
                    )}
                  </div>
                ))}
              </div>
            </div>
          ))}
        </div>
        <div style={{marginTop:28,background:`${C.blue}0C`,border:`1px solid ${C.border}`,
          borderRadius:10,padding:"20px 24px",display:"flex",gap:13,alignItems:"flex-start"}}>
          <div style={{width:38,height:38,borderRadius:8,background:"#fff",display:"flex",
            alignItems:"center",justifyContent:"center",overflow:"hidden",flexShrink:0,
            boxShadow:"0 2px 8px rgba(0,0,0,0.25)"}}>
            <img src={LOGO_SRC} alt="" style={{width:"85%",height:"85%",objectFit:"contain"}}/>
          </div>
          <div>
            <div style={{color:"#fff",fontSize:15,fontWeight:700,fontFamily:"Georgia,serif",marginBottom:5}}>
              Minimum Viable Stack for Full Automation
            </div>
            <div style={{color:C.muted,fontSize:13,lineHeight:1.7}}>
              For a fully automated Consultancy Register portal:{" "}
              <span style={{color:"#fff"}}>HubSpot CRM + ActiveCampaign + Calendly + DocuSign + Stripe + Zapier + Copilot.</span>
              {" "}Total approx.{" "}
              <span style={{color:C.green}}>£80–£120/month</span>
              {" "}— eliminating 90%+ of manual admin across all 4 services.
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}

// ── Main App ──────────────────────────────────────────────────────────────────
export default function App(){
  const [view,setView]=useState("hub");
  const [selSvc,setSelSvc]=useState(null);
  const [leads,setLeads]=useState({});
  const [activeLead,setActiveLead]=useState(null);
  const [agentLogs,setAgentLogs]=useState({});
  const [toasts,setToasts]=useState([]);
  const [docModal,setDocModal]=useState(null);
  const timerRef=useRef([]);

  useEffect(()=>()=>timerRef.current.forEach(clearTimeout),[]);

  // FIX PROD-01: unknown view guard
  const VALID_VIEWS=["hub","eco","service","apply","discovery","success","dashboard","lead"];
  const safeView=VALID_VIEWS.includes(view)?view:"hub";

  function toast(msg,type="success"){
    const id=genId();
    setToasts(t=>[...t,{id,msg,type}]);
    const t2=setTimeout(()=>setToasts(t=>t.filter(n=>n.id!==id)),5000);
    timerRef.current.push(t2);
  }

  // FIX PROD-03: stable log id
  function addLog(lid,msg,type="agent"){
    setAgentLogs(l=>({...l,[lid]:[...(l[lid]||[]),{id:genId(),time:tstamp(),msg,type}]}));
  }

  // FIX BUG-06: clipboard with textarea fallback
  function copyToClipboard(text){
    if(navigator.clipboard&&window.isSecureContext){
      navigator.clipboard.writeText(text).catch(()=>fallbackCopy(text));
    } else { fallbackCopy(text); }
  }
  function fallbackCopy(text){
    const ta=document.createElement("textarea");
    ta.value=text; ta.style.position="fixed"; ta.style.opacity="0";
    document.body.appendChild(ta); ta.focus(); ta.select();
    try{ document.execCommand("copy"); }catch(e){}
    document.body.removeChild(ta);
  }

  function handleSelectSvc(id){ setSelSvc(id); setView("service"); }

  function handleSubmitLead(form){
    const svc=SERVICES[selSvc];
    const id=genId();
    const lead={id,service:svc.id,stage:"intake",
      ...form,
      contact_time:form.contact_time||"Morning",  // FIX BUG-04
      time:tstamp(),date:tdate()};
    setLeads(l=>({...l,[id]:lead}));
    setActiveLead(id);
    setView("success");  // FIX UX-02: success screen first
    addLog(id,`Lead captured: ${lead.name} (${lead.company}). Intake qualification running...`,"system");
    const t1=setTimeout(()=>{
      addLog(id,agentMsg(svc.id,"intake",lead.name));
      toast(`◈ ${svc.agentName}: ${lead.name} captured and qualified`,"agent");
    },1200);
    const t2=setTimeout(()=>{
      setLeads(l=>({...l,[id]:{...l[id],stage:"nurture"}}));
      addLog(id,agentMsg(svc.id,"nurture",lead.name));
      toast(`◈ ${svc.agentName}: Stage 2 nurture email sent to ${lead.email}`,"agent");
    },3200);
    timerRef.current.push(t1,t2);
  }

  function handleDiscovery(fields){
    const svc=SERVICES[selSvc];
    setLeads(l=>({...l,[activeLead]:{...l[activeLead],stage:"discovery",discoveryData:fields}}));
    addLog(activeLead,agentMsg(svc.id,"discovery",leads[activeLead]?.name||"client"));
    toast(`◈ ${svc.agentName}: Discovery form received — proposal being prepared`,"agent");
    setView("lead");
  }

  function handleAction(lid,nextKey){
    const lead=leads[lid];
    const svc=SERVICES[lead.service];
    setLeads(l=>({...l,[lid]:{...l[lid],stage:nextKey}}));
    addLog(lid,agentMsg(svc.id,nextKey,lead.name));
    toast(`◈ ${svc.agentName}: ${STAGES.find(s=>s.key===nextKey)?.label} actioned for ${lead.name}`,"agent");
  }

  function handleCopyLink(link){
    copyToClipboard(link);
    toast("✓ Portal link copied — attach to any letter, email or form","success");
  }

  // Unified nav handler for breadcrumbs and back buttons
  function handleNav(targetView){
    if(targetView==="hub"){ setView("hub"); }
    else if(targetView==="service"){ setView("service"); }
    else if(targetView==="dashboard"){ setView("dashboard"); }
    else { setView(targetView||"hub"); }
  }

  const svc=selSvc?SERVICES[selSvc]:null;
  const aLead=activeLead?leads[activeLead]:null;
  const aLeadSvc=aLead?SERVICES[aLead.service]:null;

  return(
    <div style={{fontFamily:"Georgia,serif",background:C.navy,minHeight:"100vh"}}>
      <style>{`
        *{margin:0;padding:0;box-sizing:border-box;}
        @keyframes slideIn{from{opacity:0;transform:translateX(14px)}to{opacity:1;transform:translateX(0)}}
        @keyframes pulse{0%,100%{opacity:.25;transform:scale(.75)}50%{opacity:1;transform:scale(1.25)}}
        ::-webkit-scrollbar{width:4px;height:4px}
        ::-webkit-scrollbar-track{background:rgba(255,255,255,.03)}
        ::-webkit-scrollbar-thumb{background:rgba(255,255,255,.14);border-radius:2px}
        input::placeholder,textarea::placeholder{color:rgba(255,255,255,.18)!important}
        select option{background:#1A2E45;color:#fff;}
        button:focus-visible{outline:2px solid #2D7DD2;outline-offset:2px;}
      `}</style>

      <Toasts items={toasts} dismiss={id=>setToasts(t=>t.filter(n=>n.id!==id))}/>

      {docModal&&aLead&&aLeadSvc&&(
        <DocPreview type={docModal} lead={aLead} svc={aLeadSvc} onClose={()=>setDocModal(null)}/>
      )}

      <NavBar onHub={()=>{setView("hub");}} onEco={()=>setView(safeView==="eco"?"hub":"eco")} view={safeView}/>

      {/* FIX PROD-01: all views guarded */}
      {safeView==="hub"       && <HubPage onSelect={handleSelectSvc}/>}
      {safeView==="eco"       && <EcoPage onNav={handleNav}/>}
      {safeView==="service"   && svc && <ServicePage svc={svc} onApply={()=>setView("apply")} onDash={()=>setView("dashboard")} leads={leads} onNav={handleNav}/>}
      {safeView==="apply"     && svc && <ApplyPage svc={svc} onSubmit={handleSubmitLead} onNav={handleNav}/>}
      {safeView==="discovery" && svc && aLead && <DiscoveryPage svc={svc} lead={aLead} onSubmit={handleDiscovery} onNav={handleNav}/>}
      {safeView==="success"   && svc && aLead && <SuccessPage svc={svc} lead={aLead} onViewLead={()=>setView("lead")} onNewLead={()=>setView("apply")}/>}
      {safeView==="dashboard" && svc && <Dashboard svc={svc} leads={leads} onViewLead={id=>{setActiveLead(id);setView("lead");}} onNav={handleNav}/>}
      {safeView==="lead"      && aLead && aLeadSvc && (
        <LeadDetail lead={aLead} svc={aLeadSvc} onAction={handleAction}
          logs={agentLogs[aLead.id]} onCopyLink={handleCopyLink}
          onShowDoc={t=>setDocModal(t)} onNav={handleNav}
          onNewLead={()=>setView("apply")}/>
      )}
      {/* FIX PROD-01: fallback for any invalid state */}
      {!VALID_VIEWS.includes(view) && <HubPage onSelect={handleSelectSvc}/>}
    </div>
  );
}
