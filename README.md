# Cypress-Demo-Project_Task1_01Feb
Created Specs for the NopCommerce Site
describe ('Test on the NopCommerce', () => {
beforeEach(()=>{
    cy.log('Logging in to the NopCommerce Site'),
    cy.visit('https://admin-demo.nopcommerce.com/admin/'),
    cy.get('.title').should('have.text','\nWelcome, please sign in!\n'),
    cy.log('used be.enabled command')
    cy.get('#Email').should('be.enabled'),
    cy.get('#Email'). clear(),
    cy.get('#Email'). type('admin@yourstore.com'),
    cy.get('#Password').should('be.enabled'),
    cy.get('#Password').clear(),
    cy.get('#Password').type('admin'),
    cy.get('.button-1.login-button').should('be.enabled'),
    cy.get('.button-1.login-button').click()
})

afterEach(()=>{
    cy.log('Logging out to the NopCommerce Site as an Admin'),
    //cy.get('.nav-link.').eq(3).click({force:true})
    //cy.visit('/login?ReturnUrl=%2Fadmin%2F')
    cy.log('Logout element is captured through playground')
    cy.get('.navbar-nav > :nth-child(3) > .nav-link').click()
})
//it('TC:1 - Open the NopCommerce Site', () => {(
//cy.title('.brand-image-xl.logo-xl').should('eq','nopCommerce')
//cy.title().should('eq', 'nopCommerce')
//cy.title('.brand-image-xl.logo-xl').should('have.contain','nopCommerce')
//)})
it(('Tc-1: Validating the header Dashboard'),() => {(
    cy.log('Used contains command'),
    cy.get('.card-body').contains('Powered by nopCommerce'),
    //cy.get('fa.fa-bars').click()
    cy.get('.content-header').contains('Dashboard')
    //cy.get('.content-header').should('have.text', '/^Dashboard\s*$/')
    //cy.get('.content-header').should('have.text', '/^Dashboard\s$/)*')
)})

    it(('Tc-2: Validating the Menu Item Catalog and clicking on the product menu'),() => {
        (
        cy.log('Used force click'),
        cy.get('.nav-link').contains('Catalog').click({force:true}),
        cy.get('.nav-pills > :nth-child(2) > :nth-child(1) > .nav-icon').click({Force:true}),
        //cy.get('.nav-pills > :nth-child(2) > :nth-child(1) > .nav-icon'),
        //cy.get('.menu-is-opening > :nth-child(1) > p > .right')
        //cy.get('.nav-link').should('have.text','Catalog').click()
        //cy.get('.product-selector').click()
        cy.log('Used Indexing eq()'),
        cy.get('.right.fas.fa-angle-left').eq(0).click({force:true}),
        //cy.get('.nav-icon.far.fa-dot-circle').eq(0).contains('products').click({force:true}),
        //cy.get('.#unified-runner').click({force:true})
        cy.get('.nav-link').eq(6).click({force:true}),
        //cy.get('.float-left').should('have.text','Products')
        cy.get('.float-left').contains('Products'),
        cy.get('.col-form-label').eq(0).type('test'),
        cy.log('Used Previous Page command'),
        cy.go(-1),
        cy.get('.nav-link').eq(6).click({force:true}),
        cy.get('.float-left').contains('Products'),
        cy.get('.col-form-label').eq(0).type('test'),
        cy.get('.checkboxGroups').eq(2).click({force:true})
        //cy.get('.nav-item').eq(8).click()
        //cy.get('.right.fas.fa-angle-left').click({force:true})
        //cy.catagories.click(),
        //cy.contains('Product').click()
        //cy.get('.nav-sidebar').click()
        //cy.get('.menu-open > :nth-child(2) > :nth-child(2) > .nav-link > .nav-icon')
        //cy.get('.nav-pills > :nth-child(2) > :nth-child(1) > .nav-icon').click()
        //cy.get('.nav-icon.far.fa-dot-circle').contains('Categories').should('have.lenght',4)
        /* ==== Generated with Cypress Studio ==== */
        //cy.get('.nav-pills > :nth-child(2) > :nth-child(1)').click();
        //cy.get('[style="display: block;"] > :nth-child(1) > .nav-link > p').click();
        /* ==== End Cypress Studio ==== */
        //cy.get('.menu-is-opening > :nth-child(1)')
    )})

    it(('Tc-3: Validating the Menu Item Catalog -> Categories'),() => {
        (
        cy.log('Logging in to the NopCommerce Site'),
        cy.get('.nav-link').contains('Catalog').click({force:true}),
        cy.get('.nav-pills > :nth-child(2) > :nth-child(1) > .nav-icon').click({Force:true}),
        cy.get('.right.fas.fa-angle-left').eq(1).click({force:true}),
        cy.log('validation on the categories page'),
        cy.get('.nav-link').eq(7).click({force:true}),
        //cy.get('.nav-link').nextUntil('product Tags').should('have.length','3'),
        //cy.get('.nav-link').should('have.length','4'),
        cy.get('.float-left').should('have.contain','Categories')
        )})
        it(('Tc-4: Validating the Menu Item Catalog -> Manufracturer'),() => {
            (
        cy.log('validation on the manufacturers page'),
        cy.get('.nav-link').eq(8).click({force:true}),
        cy.get('.float-left').should('have.contain','Manufacturers')
            )})
        it(('Tc-5: Validating the Menu Item Catalog -> Product reviews'),() => {
            (
        cy.log('validation on the product reviews page'),
        cy.get('.nav-link').eq(9).click({force:true}),
        cy.get('.float-left').should('have.contain','Product reviews')
            )})

        it(('Tc-6: Validating the Menu Item Catalog -> Manufracturer'),() => {
                (
        cy.log('validation on the Product tags page'),
        cy.get('.nav-link').eq(10).click({force:true}),
        cy.get('.float-left').contains('Product tags')
 
    )}) 
    it(('Tc-7: Validating the Menu Item Attributes'),() => {
        (
        cy.get('.nav-link').contains('Catalog').click({force:true}),
        cy.get('.nav-pills > :nth-child(2) > :nth-child(1) > .nav-icon').click({Force:true}),
        cy.get('.right.fas.fa-angle-left').eq(2).click({force:true}),
        cy.log('validation on the Attributes page'),
        //cy.get('.nav-link.active').eq(1).click({force:true}),
        //cy.get('.right.fas.fa-angle-left').eq(2).click({force:true}),
        //cy.get('.nav-item').eq(14).click({force:true})
        cy.visit('/ProductAttribute/List'),
        cy.get('.float-left').should('have.contain','Product attributes'),
        cy.visit('/SpecificationAttribute/List'),
        cy.get('.float-left').should('have.contain','Specification attributes'),
        cy.visit('/CheckoutAttribute/List'),
        cy.get('.float-left').should('have.contain','Checkout attributes')  
        )})
})



